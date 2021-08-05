---
title: "Code"
description: "How to use code fields on NanoDLP."
lead: "How to use code fields on NanoDLP."
draft: false
images: []
menu:
  docs:
    parent: "manual"
toc: true
---

{{< alert icon="💡" text="This section is optional for direct control users." >}}

There are many code fields on both NanoDLP's machine settings and resin profile. Some of the most important ones are:

* Boot-up - will be run once just after NanoDLP executed
* Start / Stop / Resume print
* Before / After layer
* Dynamic cure time, speed and lifting
* Shutdown - run before shutdown button presses
* Shutter on / off - run if shutter enabled, consider possible gcodes will be send async, so it may cause issue for synchronization mechanisms

There are other fields that only support JS, variable and math functionalities:

* Dynamic lift
* Dynamic speed
* Dynamic cure time
* Dynamic wait

## How it works?

These fields being processed on-fly during printing, it could contains many NanoDLP keywords, gcode for your RAMPS or even Javascript codes.
After these fields processed result will be send to your controller board such as RAMPS and Trinamics.

Using these codes you can do many advanced things such as:

* Send command (eg. gcode) to RAMPS, projector or other controllers to move
* Synchronize movements
* Communicate with other programs
* Calculate many parameters using current status of the print and printer

## Variables

### Position

**[[LayerThickness]]**  
	Layer thickness in millimeter

**[[LayerPosition]]**  
	Absolute layer position in millimeter

**[[ZAxisHeight]]**  
	Z axis height in millimeter

**[[CurrentPosition]]**  
	Current position in millimeter

**[[StopPosition]]**  
	Absolute stop position from zero level

**[[ZLiftDistance]]**  
	Amount of lift after layer print in millimeter. The result of dynamic lifting will be used.

### Layer

**[[LayerNumber]]**  
	Current layer number

**[[TotalNumberOfLayers]]**  
	Total number of the plate layers

**[[TotalSolidArea]]**  
	Current layer's total solid area in mm^2

**[[LargestArea]]**  
	Current layer's largest solid area in mm^2

**[[SmallestArea]]**  
	Current layer's smallest solid area in mm^2

**[[AreaCount]]**  
	Current layer's total number of solid areas

### Misc

**[[ZSpeed]]**  
  Speed in micron/second, calculated from startup/min/max/slow section speeds in setup page. The result of dynamic speed will be used.

**[[CurrentAction]]**  
  Return current status/action of the printer: MoveTo, GcodeBefore, WaitBefore, DisplayLayer, WaitAfter, GcodeAfter, MoveToWait, WaitAfterList

**[[SkippedLayers]]**  
	Total number of layers skipped since the last printed layer

**[[LampHours]]**  
	The projector's lamp hours

**[[PlateName]]**  
	The current plate name

**[[PlateID]]**  
	Return Plate ID

### Laser

**[[IsBurninLayer]]**  
	If current layer is burn-in layer returns 1

**[[IsFilled]]**  
	Return 1 if layer movement for galvo happens in filled areas

**[[PosX]]**  
	Laser movement in X axis for galvo laser in mm

**[[PosY]]**  
	Laser movement in Y axis for galvo laser in mm

## Action keywords

### Control

**[[LayerChange layer]]**   
Change current layer `eg. [[LayerChange 22.1]]`

**[[PositionSet mm]]**  
  Update current absolute position `eg. [[PositionSet 22.1]]`

**[[PositionChange mm]]**  
  Update relative position update `eg. [[PositionChange -2.1]]`

**[[DisplayLayer LayerID]]**  
  Display any layer from current plate `eg. [[DisplayLayer 10]]`

**[[Blank]]**  
  Make screen blank

**[[LayerSkip Value]]**  
  For the positive values it skips a layer `eg. [[LayerSkip 1]]`
		It skips any remaining gcode and layer tasks, and starts the next layer.
		The more advanced use case example: `[[LayerSkip ((100>[[TotalSolidArea]])*(1-[[SkippedLayers]])*([[LayerNumber]]>3))]]`
		The gcode above would cause layers to be skipped after the first 3 layers if a layer before the current one has not been skipped and the difference between the previous and the current layer is less than 100 pixels.
	

**[[Delay Seconds]]**  
  Put delay `eg. [[Delay 1.23]]`

**[[Split]]**  
	Split gcode into chunks and process, each part will be processed after complete processing of the previous one. For example if a single chunk contain [[Delay]] keyword, it will delay processing of the next chunks.
		It is not functional on dynamic calculation fields such as dynamic speed.

### Synchronization

**[[WaitForDoneMessage]]**  
  Wait for *Z_move_comp* message from RAMPS or similar boards

**[[WaitForDoneMessage n]]**  
  Wait for *Z_move_comp* message from RAMPS or wait for n second. Which happens earlier

**[[MoveWait n]]**  
  Wait for number of *Z_move_comp* messages from RAMPS

**[[MoveCounterSet n]]**  
  Set n as current move counter

**[[ResponseCheck ExpectedOK BufferSize]]**  
  Helps synchronize fast moving SLS and laser SLA systems. It limits how many gcode will be send to RAMPS before waiting for response from RAMPS. It requires ok response from RAMPS after commands get completed and not after receiving them.
		*ExpectedOK* integer indicates how many OK will be received from RAMPS board.
		*BufferSize* indicates how many command should be sent out before receiving OK responses.		
		`eg. [[ResponseCheck 1 3]]`

**[[ResponseCheck]]**  
  Reset OK response counter to zero

**[[Pause]]**  
  Pause the printer, requires resume from dashboard to continue.

### Communication

**[[Net URL]]**  
  Send get request to the specified URL without waiting for the result `eg. [[Net http://example.com/api]]`

**[[NetReturn URL]]**  
  Send get request to the specified URL and send the result to RAMPS `eg. [[NetReturn http://127.0.0.1/gcode?layer=[[LayerNumber]]]]`

**[[Exec Command]]**  
  Run external command without waiting for the result `eg. [[Exec python my_python_script.py]]`

**[[ExecReturn Command]]**  
  Run external command and send the result to RAMPS `eg. [[ExecReturn python my_python_script.py]]`

### Hardware

**[[GPIOWaitForLow]]**  
  Wait for *"wait pin"* GPIO to be LOW

**[[Projector Command]]**  
  Send any command to the projector `eg. [[Projector \x01\x02\x03 On]]`

**[[GPIOHigh GPIO]]**  
  Makes any GPIO HIGH `eg. [[GPIOHigh 12]]`

**[[GPIOLow GPIO]]**  
  Makes any GPIO Low




## Javascript support

{{< alert icon="👉" text="This section is intended for intermediate to advanced users." >}}

You can use Javascript (ES5) to handle advanced requirements.

Javascript need to start with [JS] and end with [/JS]. The Javascript code inside will be interpreted and any result saved on variable called `output` will be replaced with [JS]...[/JS].

For example:
```js
M116
[JS]
var distance = [[LayerThickness]]-[[ZLiftDistance]]*[[LayerNumber]];
var xmlHttp = new XMLHttpRequest();
xmlHttp.open("GET", "https://www.nanodlp.com/speed-calculation?distance="+distance, false);
xmlHttp.send(null);
output = "G1 Z"+distance+" F"+xmlHttp.responseText;
[/JS]
M117
```

Result:

```gcode 
M116
G1 Z22.25 F100
M117
```

## Dynamic fields

* Using dynamic fields, NanoDLP will ignore any static value.
* For negative dynamic lift, static lift value from the profile will be used.

For more details about how to use dynamic values, you can check out [this guide](https://docs.google.com/document/d/1ySVb57AXCVfBFSr9KF7B7k3M130pJvRXXfEoh6pJP_4/edit).


## Examples

### Synchronizing movements

NanoDLP does not have knowledge of how much time it would take to finish a movement on RAMPS. There are a couple of ways to solve this problem.

#### Using [[Delay Seconds]] keyword
It is possible to put delay after each movement. It is the most widely used method.

`
G1 Z1.1
[[Delay 1.5]]
`


#### Using [[GPIOWaitForLow]] keyword

To synchronize movements nanoDLP waits for pin to be LOW. At the start of movement, controllers / drivers must make this pin HIGH and at the end of movement make it LOW. Maximum delay for detection is 1ms.

`
G1 Z1.1
[[GPIOWaitForLow]]
`


#### Using [[WaitForDoneMessage]] keyword

By using marlin or any other NanoDLP compatible RAMPS firmware you can achieve sync movements. After seeing this keyword nanoDLP will wait for *Z_move_comp* response from RAMPS.

`
G1 Z1.1
[[WaitForDoneMessage]]
`


#### Using [[ResponseCheck ExpectedOK BufferSize]] keyword
If the firmware you are using on the controller board send ok response after execution of each command, you can use this command to synchronize movements.

`
[[ResponseCheck]]
G1 X1.1
[[ResponseCheck 1 1]]
`		

### Crash Recovery

Using the right settings is the key to crash recovery and to benefit from nanoDLP in full potential. A way to do this is to delegate positioning to nanoDLP.

Follow the sample codes below to understand how to delegate positioning to nanoDLP. By doing so in addition to crash recovery, printer stop and other functions also will start working.

Start of Print

```
G90 ; Put positioning in absolute mode
G28 ; Homing
[[WaitForDoneMessage]] ; Wait until movement is completed, it requires firmwares to get patched for Z_move_comp, if you do not want to use patched firmware you can use [[Delay n.n]] instead
[[PositionSet 0]] ; Set current position on nanodlp so it could be recovered in case of failure
```

Before Layer

```
G1 Z[[LayerPosition]] ; Move to layer position
[[WaitForDoneMessage]] ; Wait for the movement to get finished
[[PositionSet [[LayerPosition]]]] ; Save layer position as the current position
```

After Layer

```
G1 Z{[[LayerPosition]]+[[ZLiftDistance]]} ; Lift to wait position
[[WaitForDoneMessage]] ; Wait for the movement to get finished
[[PositionChange [[ZLiftDistance]]]] ; Again update position
```

Resume Print

```
G90 ; Put positioning in absolute mode
G92 Z[[CurrentPosition]] Y0 X0 ; System crashed so we need to recover current position from NanoDLP and set it on RAMP
G1 Z[[LayerPosition]] ; Move to layer position
```

## GCODE

Gcode is a language being used by major RAMPS firmwares such as Marlin and GRBL. It helps do many different hardware actions.
For more information on main commands and compatibility check [RepRap gcode page](https://reprap.org/wiki/G-code).

## Async Codes

Shutter codes being processed in parallel, it is very important to consider synchronization mechanism before using async gcode inputs. As it may cause issue on synchronization as it does not guaranteed, when these codes being reached RAMPS board, which may cause printer stalls. It is better to move shutter open/close codes to before/after layer code inputs on profile level.
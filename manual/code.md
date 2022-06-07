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
* During cure time - run once cure starts
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

### Async codes

Shutter codes being processed in parallel, it is very important to consider synchronization mechanism before using async gcode inputs. As it may cause issue on synchronization as it does not guaranteed, when these codes being reached controller board, which may cause printer stalls. It is better to move shutter open/close codes to before/after layer code inputs on profile level.

### GCODE

Gcode is a language being used by major controller board firmwares such as Marlin and GRBL. It helps do many different hardware actions.
For more information on main commands and compatibility check [RepRap gcode page](https://reprap.org/wiki/G-code).

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

**[[Pause]]**  
  Pause the printer, requires resume from dashboard to continue.

### Synchronization
NanoDLP when used with shield, could not detect how much time it would takes to finish a movement. There are a couple of ways to solve this problem.

Checkout [Troubleshoot Issues]({{< ref "troubleshoot" >}}) for more delays on possible problems could be caused by wrong synchronization.

#### Using [[MoveWait n]] and [[MoveCounterSet n]] keyword
By using marlin or any other NanoDLP compatible firmware you can synchronize movements. After this keyword nanoDLP will wait for *Z_move_comp* response from the shield.

**[[MoveWait n]]**  
  Wait for number of *Z_move_comp* messages from RAMPS or similar boards.

**[[MoveCounterSet n]]**  
  Set n as current move counter

```gcode
[[MoveCounterSet 0]]
G1 Z10 F200
[[MoveWait 1]]
```
#### Using [[GPIOWaitForLow]] keyword

To synchronize movements nanoDLP waits for pin to be LOW. At the start of movement, controllers / drivers must make this pin HIGH and at the end of movement make it LOW. Maximum delay for detection is 1ms.

```gcode
G1 Z1.1
[[GPIOWaitForLow]]
```

#### Using [[ResponseCheck ExpectedOK BufferSize]] keyword
If the firmware you are using on the controller board send ok response after execution of each command, you can use this command to synchronize movements.

**[[ResponseCheck ExpectedOK BufferSize]]**  
  Helps synchronize fast moving SLS and laser SLA systems. It limits how many gcode will be send to RAMPS before waiting for response from RAMPS. It requires ok response from RAMPS after commands get completed and not after receiving them.
	*ExpectedOK* integer indicates how many OK will be received from RAMPS board.
	*BufferSize* indicates how many command should be sent out before receiving OK responses.	
	`eg. [[ResponseCheck 1 3]]`

**[[ResponseCheck]]**  
  Reset OK response counter to zero

```gcode
[[ResponseCheck]]
G1 X1.1
[[ResponseCheck 1 1]]
```

#### Using [[WaitForDoneMessage]] keyword

By using marlin or any other NanoDLP compatible firmware you can achieve sync movements. After this keyword nanoDLP will wait for *Z_move_comp* response from the shield. Not suitable for fast moving printers.

**[[WaitForDoneMessage n]]**  
  Wait for *Z_move_comp* message from RAMPS or wait for n second. Which happens earlier.

```gcode
G1 Z1.1
[[WaitForDoneMessage]]
```

#### Using [[Delay Seconds]] keyword
It is possible to put delay after each movement. It is the most widely used method.

```gcode
G1 Z1.1
[[Delay 1.5]]
```

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

### Accessing NanoDLP context

{{< alert icon="👉" text="Global context discussed here may change without notice. Use with cautious." >}}

You are able to access NanoDLP internal variables using Javascript functionality.

For example:
```js
[JS]
var nano = nanodlpContext();
output = nano["Config"]["Name"];
[/JS]
```

Result:

```
Your printer name
```

Full list of available variables on the context

```go
Config
    Name                string
    Lang                string
    Email               string
    PrinterID           int
    Port                int
    PrinterType         uint8
    ZAxisPin            uint8
    DirectionPin        uint8
    ReverseDirectionPin uint8
    LimitPin            uint8
    LimitPinB           uint8
    LimitPinMode        uint8
    LimitPinReset       uint8
    WaitPin             uint8
    EnablePin           uint8
    EnablePinState      uint8
    EnablePinMode       uint8
    FaultPin            uint8
    FaultPinState       uint8
    ShutterPin          uint8
    ShutterType         uint8
    ShutterMode         uint8
    ShutterOpen         uint
    ShutterClose        uint
    ShutterOpenGcode    string
    ShutterCloseGcode   string
    ShutterSignalLength uint
    FanOnGcode          string
    FanOffGcode         string
    MaxSpeed            int64
    MinSpeed            int64
    StartupSpeed        int64
    StopPositionMm      float64
    ResinDistanceMm     float64
    ZAxisHeight         int32
    MotorDegree         float64
    MicroStep           float64
    LeadscrewPitch      float64
    LCDType             uint8
    LCDAdress           uint8
    LCDPath             string
    ShieldType          uint8
    ShieldEncoding      uint8
    ShieldI2CAddress    uint8
    ShieldUSBAddress    string
    ShieldSpeed         int
    ShieldBootup        string
    ShieldShutdown      string
    ShieldStart         string
    ShieldResume        string
    ShieldPause         string
    ShieldUnpause       string
    ShieldFinish        string
    ShieldForceStop     string
    ShieldAxisMode      uint8 // 0 Zero bottom 1 top bottom
    ShieldPositioning   uint8 // 0 Relative  1 Absolute
    ManualMoveGcode     string
    TopGcode            string
    BottomGcode         string
    CalibrationGcode    string
    CameraFrequency     int8
    CameraStore         int8
    CameraCommand       string
    ShutdownPin         uint8
    ProjectorWidth      int
    ProjectorHeight     int
    ProjectorType       uint8
    ProjectorPowerCycle uint8
    ProjectorSpeed      int
    ProjectorAddress    string
    ProjectorOn         string
    ProjectorOff        string
    ProjectorLampQuery  string
    ProjectorLampEffect float32
    ProjectorOnSyscall  string
    ProjectorOffSyscall string
    ProjectorWarmup     float64
    DisplayController   uint8
    ImageMirror         uint8
    LightOutputFormula  string
    BarrelFactor        float64
    BarrelX             int
    BarrelY             int
    FBPath              string
    XYRes               float64
    YRes                float64
    Mute                uint8
    DisplayID           uint32
    DefaultProfile      int
    SpeedFormula        string
    RemoteSlicer        string
    PressureType        uint8
    PressureAddress     string
    PressureSpeed       int
    PressureRegex       string
    PressureDebug       bool
    ScaleClockPin       uint8
    ScaleDataPin        uint8
    OpenScaleAddress    string
    Theme               uint8
    CustomValues        map[string]string
    AutoSlice           uint8
    PreviewGenerate     uint8
    PreviewWidth        int
    PreviewHeight       int
    USBDisplayAddress   string

Layer
	PlateID        int
	LayerID        int
	ShieldAxisMode uint8

Plate
	PlateID               int
	ProfileID             int
	CreatedDate           time.Time
	StopLayers            string
	Path                  string
	LowQualityLayerNumber int
	AutoCenter            uint8
	Updated               uint64
	LastPrint             uint64
	PrintTime             int64
	PrintEst              int64
	ImageRotate           uint8
	MaskEffect            float32
	XRes                  float64
	YRes                  float64
	ZRes                  float64
	MultiCure             string
	MultiThickness        string
	CureTimes             []float64
	DynamicThickness      []float32
	Offset                float32
	OverHangs             []int
	Risky                 bool
	IsFaulty              bool
	Repaired              bool
	FaultyLayers          []int
	Corrupted             bool             `form:"-"`
	TotalSolidArea        float32          `form:"-"`
	FillAreas             []area.LayerInfo `json:"-" form:"-"`
	BlackoutData          string           `form:"-"`
	LayersCount           int              `form:"-"`
	Rectangles            RectangleStruct  `json:"-" form:"-"`
	Processed             bool             `form:"-"`
	CustomDir             string           `json:"-" form:"-"`
	Status                uint8            `json:"-" form:"-"`
	Feedback              bool
	PrintID               int64
	MC                    format.MultiCure
	boundary.Boundaries

Profile
	ResinID                int
	ProfileID              int
	Title                  string
	Desc                   string
	ResinPrice             float32
	ZStepWait              int64
	SlowSectionHeight      float32
	SlowSectionStepWait    int64
	TopWait                float32
	WaitHeight             float32
	CureTime               float32
	DynamicWaitAfterLift   string
	DynamicCureTime        string
	DynamicSpeed           string
	DynamicLift            string
	Depth                  float32
	WaitBeforePrint        float32
	WaitAfterPrint         float32
	JumpHeight             float32
	JumpPerLayer           int
	SupportTopWait         float32
	SupportWaitHeight      float32
	SupportLayerNumber     int
	SupportCureTime        float32
	SupportDepth           float32
	SupportWaitBeforePrint float32
	SupportWaitAfterPrint  float32
	AdaptSlicing           uint8
	AdaptSlicingMin        float32
	AdaptSlicingMax        float32
	YRes                   float64
	ZResPerc               float32
	SupportOffset          float32
	Offset                 float32
	ShutterOpenGcode       string
	ShutterCloseGcode      string
	FillColor              string
	BlankColor             string
	ShieldBeforeLayer      string
	ShieldAfterLayer       string
	PixelDiming            uint8
	DimAmount              float32
	DimWall                int
	DimSkip                uint
	TransitionalLayer      uint8
	ElephantMidExposure    uint8
	ElephantType           uint8
	ElephantAmount         float32
	ElephantWall           int
	ElephantLayers         int
	HatchingType           uint8
	HatchingWall           int
	HatchingGap            int
	HatchingOuterWall      int
	HatchingTopCap         int
	HatchingBottomCap      int
	AntiAlias              uint8
	AntiAlias3D            uint8
	AntiAlias3DDistance    float32
	AntiAlias3DMin         uint8
	AntiAliasThreshold     float32
	MultiCureGap           float32
	ImageRotate            uint8
	IgnoreMask             uint8
	ShieldStart            string
	ShieldResume           string
	ShieldFinish           string
	LaserCode              string
	Updated                uint64   

Status
	PlateID         int
	SlicingPlateID  int
	Path            string
	LayerID         int
	ResumeID        int
	LayerSinceStart int
	LayersCount     int
	PlateHeight     float32
	CurrentHeight   int32
	LayerTime       int64
	PrevLayerTime   int64
	LayerStartTime  int64
	Camera          int8
	LampHours       float32
	Panicked        bool `json:"-"`
	PanicRow        int
	Serial          string `json:"-"`
	ip              string
	State           Mode   `json:"-"`
	Build           string `json:"-"`
	Wifi            string `json:"-"`
	Version         int    `json:"-"`
	StartAfterSlice int    `json:"-"`
	Covered         bool
	Halted          bool `json:"-"`
	ForceStop       bool `json:"-"`
	Printing        bool `json:"-"`
	Paused          bool `json:"-"`
	AutoShutdown    bool `json:"-"`
	Cast            bool `json:"-"`

Stat
    TotalCureTime       float32
	TotalPrintTime      float32
	TotalLayers         int64
	TotalPlatePrints    int
	TotalCompletePrints int

```

## Dynamic fields

The result of equations will be used as a value for relevant operation. It could includes JS (including external calls), equations and etc.

* Using dynamic fields, NanoDLP will ignore any static value.
* For negative values, static values will be used.

For more details about how to use dynamic values, you can check out [dynamic value guide](https://docs.google.com/document/d/1ySVb57AXCVfBFSr9KF7B7k3M130pJvRXXfEoh6pJP_4/edit).


## Crash recovery

Using the right settings is the key to crash recovery and to benefit from nanoDLP in full potential. A way to do this is to delegate positioning to nanoDLP.

Follow the sample codes below to understand how to delegate positioning to nanoDLP. By doing so in addition to crash recovery, printer stop and other functions also will start working.

Start of Print

```
G90 ; Put positioning in absolute mode
[[MoveCounterSet 0]]
G28 ; Homing
[[MoveWait 1]] ; Wait until movement is completed, it requires firmwares to get patched for Z_move_comp, if you do not want to use patched firmware you can use [[Delay n.n]] instead
[[PositionSet 0]] ; Set current position on nanodlp so it could be recovered in case of failure
```

Before Layer

```
[[MoveCounterSet 0]]
G1 Z[[LayerPosition]] ; Move to layer position
[[MoveWait 1]] ; Wait for the movement to get finished
[[PositionSet [[LayerPosition]]]] ; Save layer position as the current position
```

After Layer

```
[[MoveCounterSet 0]]
G1 Z{[[LayerPosition]]+[[ZLiftDistance]]} ; Lift to wait position
[[MoveWait 1]] ; Wait for the movement to get finished
[[PositionChange [[ZLiftDistance]]]] ; Again update position
```

Resume Print

```
G90 ; Put positioning in absolute mode
G92 Z[[CurrentPosition]] Y0 X0 ; System crashed so we need to recover current position from NanoDLP and set it on RAMP
G1 Z[[LayerPosition]] ; Move to layer position
```

## Examples

You can find advanced examples of code capabilities.

### Accurate cure times

As displays getting higher resolution (eg. 8K), cure time may get less accurate as large amount of data should be transferred to GPU. You can use following trick to remove any inaccuracy by delegating cure time duration to shield.

Assume you are using M104 to turn uv light on and M105 to off. Use below code on during cure code input on profile. Better to use zero as cure time (burn-in, normal and dynamic), as it will be controlled by below code, additional cure time will be added on top.

```
[[MoveCounterSet 0]]
G4 P100; Wait for 100ms to make sure resin settled
M104; Turn on the UV LED
G4 P18000; Wait for 18 seconds
[[MoveWait 2]] ; Wait until shield returns Z_move_done which indicate G4 P18000 finished
M105; Turn off the UV LED
```

### Turn on/off display

Following commands are suitable for sending command through HDMI-CEC.
You can find some example, they may not compatible with your display.

```
[[Exec /opt/vc/bin/tvservice -o]] ; Cut the signal
[[Exec /opt/vc/bin/tvservice -p]] ; Restore the signal
[[Exec echo "standby 0" | cec-client -s]]; Turn off display
[[Exec echo "on 0" | cec-client -s]]; Turn on display
```

### Light output

Light output of LED and projector lamps decrease by time. To keep output same for every prints you need to adjust light output. 

It is specially important for sensitive dental resins.

This modifier's unit is percentage and it effect color inputs on all profiles.

0 means no change to output. 80 means 80% increase in light output. -80 means 80% decrease in light output.

For example if profile render color is total white (#FFFFFF), -100% modifier make it total black (#000000).
It only calculated once before slicing of a plate and only effects newly generated plates from source files.

You should use Light Output Formula input on machine settings page.

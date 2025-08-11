---
title: "Machine Configuration"
description: "Complete guide to NanoDLP machine settings, hardware configuration, and system parameters for optimal printer performance."
lead: "Learn how to configure your NanoDLP printer hardware, pins, motors, displays, and advanced features."
draft: false
menu:
  docs:
    parent: "manual"
images: []
toc: true
---

## Overview

Machine configuration in NanoDLP controls the fundamental hardware behavior, pin assignments, motor characteristics, and system-level settings. These configurations define how your printer interacts with its hardware components and determine the overall printing capabilities.

## Basic Configuration

### General Settings
- **Name**: Printer identification name
- **Language**: Interface language selection
- **Email**: Contact email for notifications
- **WiFi Country**: WiFi regulatory compliance
- **Printer ID**: Unique printer identifier
- **Port**: Web interface port number
- **View Mode**: Display mode configuration
- **Printer Type**: Printer technology selection

## Hardware Pin Configuration

### Z-Axis Control
- **Z Axis Pin**: Pin number for Z-axis stepper motor
- **Direction Pin**: Pin for motor direction control
- **Reverse Direction Pin**: Pin for reverse direction (if applicable)
- **Limit Pin**: Z-axis limit switch pin
- **Limit Pin B**: Secondary limit switch pin
- **Limit Pin Mode**: Limit switch behavior mode
- **Limit Pin Reset**: Limit switch reset pin

### System Control Pins
- **Wait Pin**: Wait condition monitoring pin
- **Enable Pin**: Motor enable/disable control pin
- **Enable Pin State**: Enable pin active state
- **Enable Pin Mode**: Enable pin behavior mode
- **Fault Pin**: Fault condition monitoring pin
- **Fault Pin State**: Fault pin active state
- **Shutdown Pin**: System shutdown control pin

### Shutter Control
- **Shutter Pin**: Shutter mechanism control pin
- **Shutter Type**: Type of shutter mechanism
- **Shutter Mode**: Shutter operation mode
- **Shutter Open**: Shutter open timing
- **Shutter Close**: Shutter close timing
- **Shutter Open/Close Gcode**: G-code commands for shutter control
- **Shutter Signal Length**: Duration of shutter control signals

### Fan Control
- **Fan On Gcode**: G-code to turn on cooling fan
- **Fan Off Gcode**: G-code to turn off cooling fan

## Motor Configuration

### Speed Settings
- **Max Speed**: Maximum allowed movement speed
- **Min Speed**: Minimum required movement speed
- **Startup Speed**: Initial movement speed

### Motor Characteristics
- **Motor Degree**: Stepper motor step angle
- **Micro Step**: Microstepping configuration
- **Leadscrew Pitch**: Leadscrew thread pitch for Z-axis

### Movement Control
- **Stop Position Mm**: Safe stop position in millimeters
- **Resin Distance Mm**: Distance from resin surface to platform

## Display Configuration

### LCD Settings
- **LCD Type**: Type of LCD display
- **LCD Address**: I2C address for LCD communication
- **LCD Path**: Path to LCD device file

### Shield Configuration
- **Shield Type**: Type of display shield
- **Shield Encoding**: Communication encoding method
- **Shield I2C Address**: I2C address for shield communication
- **Shield USB Address**: USB address for shield communication
- **Shield Speed**: Communication speed with shield

### Shield Commands
- **Shield Bootup**: Bootup sequence commands
- **Shield Shutdown**: Shutdown sequence commands
- **Shield Start**: Start printing commands
- **Shield Resume**: Resume printing commands
- **Shield Pause**: Pause printing commands
- **Shield Unpause**: Unpause printing commands
- **Shield Finish**: Finish printing commands
- **Shield Force Stop**: Emergency stop commands
- **Shield Axis Mode**: Z-axis zeroing mode (0=bottom, 1=top/bottom)
- **Shield Positioning**: Positioning mode (0=relative, 1=absolute)

## Projector Configuration

### Basic Settings
- **Projector Width**: Projector resolution width
- **Projector Height**: Projector resolution height
- **Projector Type**: Type of projector technology
- **Projector Power Cycle**: Power cycling behavior
- **Projector Speed**: Projector communication speed
- **Projector Address**: Network address for projector

### Power Management
- **Projector On**: Command to turn on projector
- **Projector Off**: Command to turn off projector
- **Projector Lamp Query**: Command to query lamp status
- **Projector Lamp Effect**: Lamp effect intensity
- **Projector On Syscall**: System call for projector power on
- **Projector Off Syscall**: System call for projector power off
- **Projector Warmup**: Warmup time in seconds

## Build Area Configuration

### Vat Dimensions
- **Vat Width**: Width of resin vat in millimeters
- **Vat Height**: Height of resin vat in millimeters

### File Management
- **FB Path**: File browser path
- **Disp Conn**: Display connection configuration

## Resolution and Scaling

### Resolution Settings
- **X Res**: X-axis resolution in pixels per millimeter
- **Y Res**: Y-axis resolution in pixels per millimeter

### Slicer Options
- **Slicer Export Format**: Export format selection (0=PNG, 2=BMP)
- **Preview Width/Height**: Preview image dimensions
- **Area Padding**: Build area padding settings
- **Barrel Factor**: Barrel distortion correction factor
- **Barrel X/Y**: Barrel distortion center coordinates
- **Image Mirror**: Image mirroring options
- **Display Controller**: Display controller type
- **Light Output Formula**: Light output calculation formula

## Advanced Features

### Pressure Control
- **Pressure Type**: Type of pressure monitoring
- **Pressure Address**: Pressure sensor address
- **Pressure Speed**: Pressure sensor communication speed
- **Pressure Regex**: Pressure data parsing pattern
- **Pressure Debug**: Enable pressure debugging

### Scale Integration
- **Scale Clock Pin**: Scale clock signal pin
- **Scale Data Pin**: Scale data signal pin
- **OpenScale Address**: OpenScale device address

### Board Parser
- **Board Parser**: Custom board communication parser

### Custom Values
- **Custom Values**: User-defined configuration values

## System Features

### Automation
- **Auto Slice**: Automatic slicing configuration
- **Preview Generate**: Automatic preview generation

### Display Integration
- **USB Display Address**: USB display device address
- **USB Display Baud**: USB display communication speed
- **USB Path**: USB device path

### System Identification
- **UUID**: Unique system identifier
- **Theme**: User interface theme selection

## Configuration Management

### Saving and Loading
- **Save()**: Save current configuration to file
- **Load(file)**: Load configuration from specified file

### Utility Functions
- **ZAxisHeightMicron()**: Get Z-axis height in microns
- **PlatformSize()**: Calculate platform dimensions
- **ZPulseSize()**: Calculate Z-axis pulse size
- **ResinAmount()**: Calculate resin volume
- **ResinMicron()**: Get resin height in microns
- **MicronToPulse()**: Convert microns to motor pulses
- **PulseToMicron()**: Convert motor pulses to microns
- **DisplayRatio()**: Calculate display aspect ratio
- **USBFolders()**: Get USB storage folders

## Best Practices

### Pin Configuration
- Use dedicated pins for critical functions
- Avoid pin conflicts between different systems
- Test pin assignments before final configuration
- Document pin assignments for future reference

### Motor Tuning
- Start with conservative speed settings
- Gradually increase speeds while monitoring performance
- Calibrate microstepping for smooth operation
- Verify leadscrew pitch measurements

### Display Setup
- Ensure proper I2C address configuration
- Test communication before finalizing settings
- Configure appropriate communication speeds
- Set up proper power management sequences

### Safety Considerations
- Always test emergency stop functions
- Verify limit switch operation
- Test shutdown procedures
- Monitor fault conditions

## Troubleshooting

### Common Issues
- **Pin Conflicts**: Check for duplicate pin assignments
- **Communication Errors**: Verify addresses and speeds
- **Motor Issues**: Check microstepping and speed settings
- **Display Problems**: Verify I2C addresses and connections

### Debug Tools
- Use terminal interface for real-time monitoring
- Check system logs for error messages
- Test individual components in isolation
- Verify power supply stability

## Related Topics

- [Profile Management]({{<ref "profiles">}})
- [Hardware Setup]({{<ref "hardware">}})
- [Display Calibration]({{<ref "display-calibration">}})
- [Settings Overview]({{<ref "settings">}})
- [WiFi Configuration]({{<ref "guide/raspberry-pi-display">}})

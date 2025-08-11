---
title: "Serial Terminal"
description: "Complete guide to using the serial terminal for direct G-code communication and printer control in NanoDLP."
lead: "Learn how to use the built-in serial terminal for advanced printer control and debugging."
draft: false
menu:
  docs:
    parent: "manual"
images: []
toc: true
---

# Serial Terminal

## Overview
The NanoDLP Serial Terminal provides direct communication with your 3D printer's controller board, allowing you to send G-code commands, monitor responses, and perform advanced printer operations. This feature is essential for debugging, calibration, and advanced printer control.

## Features

### Direct Communication
- **Real-time Communication**: Direct serial connection to printer controller
- **G-code Support**: Send and receive standard G-code commands
- **Response Monitoring**: View real-time responses from the printer
- **Command History**: Track sent commands and responses

### Advanced Control
- **Manual Control**: Direct control over printer movements
- **Parameter Adjustment**: Modify printer parameters in real-time
- **Status Monitoring**: Monitor printer status and sensor readings
- **Emergency Control**: Emergency stop and safety commands

### Debugging Tools
- **Error Reporting**: View detailed error messages
- **Status Information**: Monitor printer health and status
- **Performance Metrics**: Track printer performance data
- **Troubleshooting**: Identify and resolve printer issues

## How It Works

### Connection Process
1. **Serial Port Detection**: System detects available serial ports
2. **Baud Rate Configuration**: Set appropriate communication speed
3. **Connection Establishment**: Establish serial communication link
4. **Handshake Verification**: Verify communication with printer

### Communication Protocol
- **G-code Standard**: Industry-standard G-code commands
- **Response Handling**: Process and display printer responses
- **Error Detection**: Identify communication errors
- **Timeout Management**: Handle communication timeouts

## User Interface

### Terminal Display
- **Command Output**: Display of sent commands
- **Response Display**: Show printer responses
- **Status Information**: Current printer status
- **Error Messages**: Display error and warning messages

### Input Controls
- **Command Input**: Text field for G-code commands
- **Send Button**: Execute entered commands
- **Command History**: Access to previously sent commands
- **Auto-complete**: G-code command suggestions

### Display Options
- **Scroll Control**: Navigate through terminal output
- **Text Size**: Adjustable text size for readability
- **Color Coding**: Different colors for commands, responses, and errors
- **Timestamp Display**: Show command execution timing

## Common G-code Commands

### Movement Commands
- **G0/G1**: Rapid/Linear movement
- **G28**: Home all axes
- **G29**: Bed leveling
- **G90/G91**: Absolute/Relative positioning

### Temperature Control
- **M104**: Set hotend temperature
- **M140**: Set bed temperature
- **M105**: Get temperature readings
- **M109**: Wait for hotend temperature

### Printer Control
- **M84**: Disable steppers
- **M112**: Emergency stop
- **M115**: Get firmware version
- **M503**: Print settings

### Advanced Commands
- **M501**: Load settings from EEPROM
- **M500**: Save settings to EEPROM
- **M851**: Set Z probe offset
- **M420**: Enable/disable bed leveling

## Configuration Options

### Serial Settings
- **Port Selection**: Choose appropriate serial port
- **Baud Rate**: Set communication speed (typically 115200)
- **Data Bits**: Configure data bit count
- **Parity**: Set parity checking
- **Stop Bits**: Configure stop bit count

### Terminal Options
- **Auto-scroll**: Enable/disable automatic scrolling
- **Command Echo**: Show sent commands in output
- **Response Timeout**: Set response wait time
- **Buffer Size**: Configure input/output buffer sizes

### Display Settings
- **Text Color**: Customize text colors
- **Font Size**: Adjust display font size
- **Line Spacing**: Set line spacing
- **Background**: Choose terminal background

## Best Practices

### Command Usage
1. **Test Commands**: Test commands on small movements first
2. **Verify Responses**: Always check printer responses
3. **Use Safe Values**: Start with conservative parameter values
4. **Document Changes**: Keep records of parameter modifications

### Safety Considerations
1. **Emergency Stop**: Know how to use emergency stop
2. **Movement Limits**: Understand printer movement limits
3. **Temperature Safety**: Monitor temperature settings
4. **Backup Settings**: Save current settings before changes

### Troubleshooting
1. **Connection Issues**: Check serial port and cable
2. **Communication Errors**: Verify baud rate and settings
3. **Command Failures**: Check command syntax and parameters
4. **Response Problems**: Monitor for error messages

## Advanced Features

### Scripting Support
- **Command Sequences**: Execute multiple commands in sequence
- **Conditional Logic**: Add conditional command execution
- **Loop Structures**: Repeat command sequences
- **Variable Support**: Use variables in commands

### Automation
- **Auto-calibration**: Automated calibration sequences
- **Batch Operations**: Process multiple commands automatically
- **Scheduled Tasks**: Execute commands at specific times
- **Event Triggers**: Respond to printer events

### Integration
- **API Access**: Programmatic terminal access
- **Logging**: Comprehensive command and response logging


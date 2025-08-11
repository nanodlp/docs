---
title: "Web Interface"
description: "Complete guide to NanoDLP web interface features, API endpoints, and user interface functionality."
lead: "Learn how to use NanoDLP's web interface for printer control, file management, and system configuration."
draft: false
menu:
  docs:
    parent: "manual"
images: []
toc: true
---

## Overview

NanoDLP provides a comprehensive web-based interface for controlling your 3D printer, managing print jobs, and configuring system settings. The web interface is accessible from any device on your network and provides both user-friendly controls and advanced API endpoints.

## Core Interface

### Home Page
- **URL**: `/`
- **Access**: Guest (public)
- **Features**: 
  - Printer status overview
  - Current print progress
  - Quick access to common functions
  - System information display

### Layer Preview
- **URL**: `/layer/preview/{plateID}/{layerID}`
- **Access**: Guest (public)
- **Features**:
  - Individual layer visualization
  - Print preview for specific layers
  - Quality assessment tools

## Slicing and File Management

### Plate Management
- **Add New Plate**: Upload and prepare 3D models for printing
- **Plate Regeneration**: Regenerate plates with new settings
- **Plate Operations**: View, edit, and manage existing plates
- **Advanced Plates**: Manufacturer-level plate management

### Slicing Operations
- **Slicer Status**: Monitor current slicing progress
- **Remote Slicing**: Use external slicing services
- **Calibration**: Add calibration files for Athena system
- **Time Estimation**: Calculate print time and material usage

### File Operations
- **Upload Methods**: Web interface and REST API uploads
- **File Formats**: Support for various 3D model formats
- **Preview Generation**: Automatic preview image creation
- **File Organization**: Structured file management system

## Printer Control

### Power Management
- **Printer On/Off**: Control printer power state
- **Auto Shutdown**: Configure automatic shutdown behavior
- **Restart Options**: Restart printer or specific components

### HMI Control
- **HMI Start/Stop**: Control Human Machine Interface
- **HMI Restart**: Restart HMI system
- **HMI Status**: Monitor HMI operation

### System Operations
- **NanoDLP Reload**: Reload application without restart
- **System Restore**: Restore default settings
- **Backup/Restore**: Create and restore system backups
- **Statistics Reset**: Clear system statistics

### Upgrade Management
- **NanoDLP Upgrades**: Online and offline upgrade options
- **HMI Upgrades**: Display interface updates
- **Version Management**: Track and manage software versions

## Settings and Configuration

### Machine Settings
- **PI Configuration**: Raspberry Pi specific settings
- **Setup Management**: Core system configuration
- **Custom Inputs**: User-defined configuration values
- **Timezone Settings**: System time configuration

### Hardware Configuration
- **WiFi Management**: Network configuration and management
- **Country Settings**: Regulatory compliance settings
- **Custom Sound**: Audio notification configuration
- **Custom Consumables**: Material tracking and management

### Advanced Settings
- **Manufacturer Access**: High-level configuration options
- **System Integration**: External system connections
- **Performance Tuning**: System optimization settings

## Hardware Management

### Debug Operations
- **Debug Continue**: Resume debug operations
- **System Monitoring**: Real-time system status
- **Error Logging**: Comprehensive error tracking

### Firmware Management
- **Klipper Upload**: Upload Klipper firmware
- **RAMPS Connection**: Manage RAMPS board connections
- **Board Communication**: Monitor board status

### Network Management
- **WiFi Configuration**: Set up wireless networks
- **Network Status**: Monitor connection health
- **USB Management**: Handle USB storage devices

### Terminal Interface
- **Terminal Access**: Command-line interface
- **G-code Sending**: Manual G-code execution
- **Real-time Monitoring**: Live system feedback

## File and Storage

### USB Storage
- **USB File Browser**: Navigate USB storage devices
- **File Preview**: Preview files before processing
- **File Management**: Organize and manage files

### Database Access
- **Database Files**: Access system database files
- **Configuration Export**: Export system settings
- **Data Backup**: Create data backups

## API and Integration

### REST API
- **JSON Endpoints**: Machine-readable data access
- **Authentication**: Bearer token security
- **Response Formats**: Structured data responses

### Remote Integration
- **Remote Slicing**: External slicing service integration
- **External Systems**: Connect to other software
- **Webhooks**: Event-driven notifications

## Security and Permissions

### Access Levels
- **Guest Access**: Public information and basic functions
- **User Access**: Standard user operations
- **Admin Access**: System administration functions
- **Manufacturer Access**: High-level configuration

### Authentication
- **Bearer Tokens**: Secure API access
- **Session Management**: User session handling
- **Permission Control**: Granular access control

## Monitoring and Analytics

### System Status
- **CPU Usage**: Processor utilization monitoring
- **Memory Usage**: RAM usage tracking
- **Disk Usage**: Storage space monitoring
- **Temperature**: System temperature monitoring

### Print Analytics
- **Print Statistics**: Comprehensive print data
- **Quality Metrics**: Print quality analysis
- **Performance Tracking**: System performance monitoring

### Real-time Monitoring
- **Live Updates**: Real-time status updates
- **Progress Tracking**: Print progress monitoring
- **Error Reporting**: Immediate error notifications

## User Experience Features

### Responsive Design
- **Mobile Support**: Mobile-optimized interface
- **Touch Interface**: Touch-friendly controls
- **Responsive Layout**: Adaptive screen layouts

### Accessibility
- **Keyboard Navigation**: Full keyboard support
- **Screen Reader Support**: Accessibility compliance
- **High Contrast**: Visual accessibility options

### Customization
- **Theme Selection**: Multiple interface themes
- **Language Support**: Multi-language interface
- **Custom Layouts**: User-defined interface layouts

## Troubleshooting

### Common Issues
- **Connection Problems**: Network connectivity issues
- **Authentication Errors**: Login and permission problems
- **Performance Issues**: Slow interface response
- **Display Problems**: Visual interface issues

### Debug Tools
- **Browser Console**: Client-side debugging
- **Network Monitor**: Network request analysis
- **Error Logs**: Detailed error information
- **System Logs**: Comprehensive system logging

## Best Practices

### Interface Usage
- Use modern web browsers for best compatibility
- Keep the interface open during printing for monitoring
- Use keyboard shortcuts for efficient navigation
- Bookmark frequently used pages

### Security
- Use strong passwords for admin accounts
- Regularly update access tokens
- Monitor access logs for suspicious activity
- Restrict network access when possible

### Performance
- Close unused browser tabs
- Clear browser cache regularly
- Use wired connections for critical operations
- Monitor system resources during heavy use

## Related Topics

- [Machine Configuration]({{<ref "machine-configuration">}})
- [Profile Management]({{<ref "profiles">}})
- [Hardware Setup]({{<ref "hardware">}})
- [Settings Overview]({{<ref "settings">}})
- [WiFi Configuration]({{<ref "guide/raspberry-pi-display">}})
- [Backup and Restore]({{<ref "guide/backup">}})

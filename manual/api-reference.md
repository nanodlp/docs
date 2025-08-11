---
title: "API Reference"
description: "Complete NanoDLP API reference with all endpoints, parameters, and response formats."
lead: "Comprehensive guide to NanoDLP's REST API for automation and integration."
draft: false
menu:
  docs:
    parent: "manual"
images: []
toc: true
---

## Overview

NanoDLP provides a comprehensive REST API for programmatic access to all printer functions. The API supports JSON responses and uses Bearer token authentication for secure access.

## Authentication

### Bearer Token Authentication
All protected endpoints require a Bearer token in the Authorization header:
```
Authorization: Bearer <your-token-here>
```

### Access Levels
- **Guest**: Public endpoints (no authentication required)
- **User**: Standard user operations
- **Admin**: System administration functions
- **Manufacturer**: High-level configuration access

## Base URL
```
http://your-printer-ip:port/
```

## Core Endpoints

### Home and Status

#### Get Home Page
- **URL**: `GET /`
- **Access**: Guest
- **Response**: HTML home page
- **Description**: Display home page with printer status

#### Get Home Data (JSON)
- **URL**: `GET /json/index`
- **Access**: User
- **Response**: JSON home data
- **Description**: Get home page data in JSON format

#### Get Layer Preview
- **URL**: `GET /layer/preview/{plateID}/{layerID}`
- **Access**: Guest
- **Parameters**:
  - `plateID`: Plate identifier
  - `layerID`: Layer number
- **Response**: Layer preview information
- **Description**: Preview specific layer information

### Database Access

#### Serve Database File
- **URL**: `GET /json/db/{file}`
- **Access**: User
- **Parameters**:
  - `file`: Database filename
- **Response**: Database file (octet-stream)
- **Description**: Access system database files

### Formula Calculations

#### Formula Page
- **URL**: `POST /formula`
- **Access**: Guest
- **Method**: POST
- **Response**: HTML formula page
- **Description**: Display formula calculation page

## Slicing and File Management

### Plate Management

#### Regenerate Plate (GET)
- **URL**: `GET /plate/regenerate/{PlateID}`
- **Access**: User
- **Parameters**:
  - `PlateID`: Plate identifier to regenerate
- **Response**: JSON confirmation
- **Description**: Regenerate plate with new settings

#### Regenerate Plate (POST)
- **URL**: `POST /plate/regenerate`
- **Access**: User
- **Method**: POST
- **Response**: JSON confirmation
- **Description**: Regenerate plate via POST

#### Add New Plate (Web)
- **URL**: `POST /plate/add`
- **Access**: User
- **Method**: POST
- **Response**: JSON confirmation
- **Description**: Upload new plate via web interface

#### Add New Plate (REST)
- **URL**: `POST /api/v1/job/add`
- **Access**: User
- **Method**: POST
- **Response**: JSON confirmation
- **Description**: Upload new plate via REST API

### Slicing Operations

#### Get Slicer Status
- **URL**: `GET /slicer`
- **Access**: Guest
- **Response**: JSON slicer status
- **Description**: Get current slicer status and information

#### Cancel Slicing
- **URL**: `GET /slicer/cancel`
- **Access**: User
- **Response**: JSON confirmation
- **Description**: Cancel current slicing operation

#### Remote Slicer Host
- **URL**: `POST /slicer`
- **Access**: User
- **Method**: POST
- **Response**: JSON response
- **Description**: Handle remote slicer requests

### Calibration and Estimation

#### Add Calibration
- **URL**: `POST /api/v1/athena/calibration/add/{calibrationFile}`
- **Access**: User
- **Method**: POST
- **Parameters**:
  - `calibrationFile`: Calibration filename
- **Response**: JSON confirmation
- **Description**: Add calibration file for Athena system

#### Estimate Plate
- **URL**: `GET /estimate/{profileID}/{height}`
- **Access**: User
- **Parameters**:
  - `profileID`: Profile identifier
  - `height`: Print height
- **Response**: JSON plate estimate
- **Description**: Estimate print time and material usage

## Printer Control

### Power Management

#### Turn Off Printer
- **URL**: `GET /printer/off`
- **Access**: User (printing must be stopped)
- **Response**: JSON confirmation
- **Description**: Turn off the printer

#### Toggle Auto Shutdown
- **URL**: `GET /printer/auto-shutdown/{mode}`
- **Access**: User
- **Parameters**:
  - `mode`: Shutdown mode
- **Response**: JSON confirmation
- **Description**: Toggle auto shutdown mode

### System Operations

#### Restart Printer
- **URL**: `GET /printer/restart`
- **Access**: User (printing must be stopped)
- **Response**: JSON confirmation
- **Description**: Restart the printer system

#### Reload NanoDLP
- **URL**: `GET /printer/reload`
- **Access**: User (printing must be stopped)
- **Response**: JSON confirmation
- **Description**: Reload NanoDLP application

#### Terminate Printer
- **URL**: `GET /printer/terminate`
- **Access**: User (printing must be stopped)
- **Response**: JSON confirmation
- **Description**: Terminate printer process

### HMI Control

#### Restart HMI
- **URL**: `GET /printer/hmi/restart`
- **Access**: User (printing must be stopped)
- **Response**: JSON confirmation
- **Description**: Restart Human Machine Interface

#### Stop HMI
- **URL**: `GET /printer/hmi/stop`
- **Access**: User (printing must be stopped)
- **Response**: JSON confirmation
- **Description**: Stop Human Machine Interface

#### Start HMI
- **URL**: `GET /printer/hmi/start`
- **Access**: User (printing must be stopped)
- **Response**: JSON confirmation
- **Description**: Start Human Machine Interface

### System Management

#### Reset Statistics
- **URL**: `GET /printer/stat/reset`
- **Access**: Admin
- **Response**: JSON confirmation
- **Description**: Reset printer statistics

#### Restore Default Settings
- **URL**: `GET /printer/restore-default`
- **Access**: User (printing must be stopped)
- **Response**: JSON confirmation
- **Description**: Restore printer to default settings

#### Create Backup
- **URL**: `GET /printer/backup`
- **Access**: Admin
- **Response**: JSON confirmation
- **Description**: Create backup of printer settings

#### Get Restore Page
- **URL**: `GET /printer/restore`
- **Access**: Admin
- **Response**: HTML restore page
- **Description**: Display printer restore page

#### Restore Printer
- **URL**: `POST /printer/restore`
- **Access**: Admin
- **Method**: POST
- **Response**: JSON confirmation
- **Description**: Restore printer from backup

### Upgrade Management

#### Get Upgrade Page
- **URL**: `GET /printer/upgrade`
- **Access**: Manufacturer
- **Response**: HTML upgrade page
- **Description**: Display printer upgrade page

#### Get Upgrade Information
- **URL**: `GET /printer/upgrade/info`
- **Access**: Manufacturer
- **Response**: JSON upgrade information
- **Description**: Get available upgrade information

#### Upgrade NanoDLP
- **URL**: `GET /printer/upgrade/go/{version}`
- **Access**: Manufacturer
- **Parameters**:
  - `version`: Version to upgrade to
- **Response**: JSON confirmation
- **Description**: Upgrade NanoDLP to specified version

#### Offline Upgrade
- **URL**: `POST /printer/upgrade/go`
- **Access**: Manufacturer
- **Method**: POST
- **Response**: JSON confirmation
- **Description**: Upgrade from offline file

#### Upgrade HMI
- **URL**: `GET /printer/upgrade/dsi/{version}`
- **Access**: Manufacturer
- **Parameters**:
  - `version`: Version to upgrade to
- **Response**: JSON confirmation
- **Description**: Upgrade HMI to specified version

## Settings and Configuration

### PI Settings

#### Edit PI Settings Page
- **URL**: `GET /printer/edit/pi`
- **Access**: Manufacturer
- **Response**: HTML PI settings page
- **Description**: Display PI settings editing page

#### Save PI Settings
- **URL**: `POST /printer/edit/pi`
- **Access**: Manufacturer
- **Method**: POST
- **Response**: JSON confirmation
- **Description**: Save PI settings

### Setup Management

#### Setup Page
- **URL**: `GET /setup`
- **Access**: Manufacturer
- **Response**: HTML setup page
- **Description**: Display setup configuration page

#### Export Nano Support
- **URL**: `GET /setup/export/nanosupport`
- **Access**: Manufacturer
- **Response**: Nano support export file
- **Description**: Export nano support configuration

#### Export Setup
- **URL**: `GET /setup/export`
- **Access**: Manufacturer
- **Response**: Setup export file
- **Description**: Export setup configuration

#### Import Setup
- **URL**: `POST /setup/import`
- **Access**: Manufacturer
- **Method**: POST
- **Response**: JSON confirmation
- **Description**: Import setup configuration

#### Fetch Setup
- **URL**: `POST /setup/fetch`
- **Access**: Manufacturer
- **Method**: POST
- **Response**: JSON confirmation
- **Description**: Fetch setup configuration

#### Save Setup
- **URL**: `POST /setup`
- **Access**: Manufacturer
- **Method**: POST
- **Response**: JSON confirmation
- **Description**: Save setup configuration

### Custom Configuration

#### Get Custom Input
- **URL**: `GET /setup/custom-input/get/{name}`
- **Access**: Manufacturer
- **Parameters**:
  - `name`: Input name
- **Response**: JSON custom input value
- **Description**: Get custom input value

#### Set Custom Input
- **URL**: `POST /setup/custom-input/set/{name}`
- **Access**: Manufacturer
- **Method**: POST
- **Parameters**:
  - `name`: Input name
- **Response**: JSON confirmation
- **Description**: Set custom input value

#### Custom Inputs Page
- **URL**: `GET /setup/custom-inputs`
- **Access**: Manufacturer
- **Response**: HTML custom inputs page
- **Description**: Display custom inputs page

#### Save Custom Inputs
- **URL**: `POST /setup/custom-inputs`
- **Access**: Manufacturer
- **Method**: POST
- **Response**: JSON confirmation
- **Description**: Save custom inputs configuration

### Audio and Consumables

#### Custom Sound Page
- **URL**: `GET /setup/custom-sound`
- **Access**: Manufacturer
- **Response**: HTML custom sound page
- **Description**: Display custom sound page

#### Save Custom Sound
- **URL**: `POST /setup/custom-sound`
- **Access**: Manufacturer
- **Method**: POST
- **Response**: JSON confirmation
- **Description**: Save custom sound configuration

#### Custom Consumables Page
- **URL**: `GET /setup/custom-consumables`
- **Access**: Manufacturer
- **Response**: HTML custom consumables page
- **Description**: Display custom consumables page

#### Reset Consumable
- **URL**: `GET /setup/custom-consumables/reset/{name}`
- **Access**: Manufacturer
- **Parameters**:
  - `name`: Consumable name
- **Response**: JSON confirmation
- **Description**: Reset consumable counter

#### Save Custom Consumables
- **URL**: `POST /setup/custom-consumables`
- **Access**: Manufacturer
- **Method**: POST
- **Response**: JSON confirmation
- **Description**: Save custom consumables configuration

### System Configuration

#### Timezone Page
- **URL**: `GET /setup/timezone`
- **Access**: User
- **Response**: HTML timezone page
- **Description**: Display timezone configuration page

#### Get Timezone JSON
- **URL**: `GET /json/setup/timezone`
- **Access**: User
- **Response**: JSON timezone data
- **Description**: Get timezone data as JSON

#### Save Timezone
- **URL**: `POST /setup/timezone`
- **Access**: User
- **Method**: POST
- **Response**: JSON confirmation
- **Description**: Save timezone configuration

#### Save WiFi Country
- **URL**: `POST /setup/wifi/country`
- **Access**: User
- **Method**: POST
- **Response**: JSON confirmation
- **Description**: Save WiFi country configuration

## Hardware Management

### Debug Operations

#### Continue Debug
- **URL**: `GET /debug/continue`
- **Access**: Manufacturer
- **Response**: JSON confirmation
- **Description**: Continue debug operation

#### Upload Klipper
- **URL**: `POST /printer/upload/klipper`
- **Access**: User
- **Method**: POST
- **Response**: JSON confirmation
- **Description**: Upload Klipper firmware

#### Reconnect RAMPS
- **URL**: `GET /ramps/reconnect`
- **Access**: User (printing must be stopped)
- **Response**: JSON confirmation
- **Description**: Reconnect to RAMPS board

### Network Management

#### WiFi Page
- **URL**: `GET /wifi` or `GET /wifi/{details}`
- **Access**: User
- **Parameters**:
  - `details`: Optional WiFi details
- **Response**: HTML WiFi page
- **Description**: Display WiFi configuration page

#### Connect WiFi
- **URL**: `POST /wifi/connect`
- **Access**: User
- **Method**: POST
- **Response**: JSON confirmation
- **Description**: Connect to WiFi network

#### Get WiFi List
- **URL**: `GET /json/wifi`
- **Access**: User
- **Response**: JSON WiFi networks
- **Description**: Get available WiFi networks

#### Get Network Status
- **URL**: `GET /json/network/status`
- **Access**: User
- **Response**: JSON network status
- **Description**: Get network connection status

### Terminal and G-code

#### Terminal Page
- **URL**: `GET /term`
- **Access**: User
- **Response**: HTML terminal page
- **Description**: Display terminal interface page

#### Terminal Data
- **URL**: `GET /term-io`
- **Access**: User
- **Response**: JSON terminal data
- **Description**: Get terminal data stream

#### Send G-code
- **URL**: `POST /term-io` or `POST /gcode`
- **Access**: User
- **Method**: POST
- **Response**: JSON confirmation
- **Description**: Send manual G-code command

### File Management

#### Get USB Files
- **URL**: `GET /json/usb`
- **Access**: User
- **Response**: JSON USB files
- **Description**: Get list of USB files

#### Preview USB File
- **URL**: `GET /usb/preview/{file}`
- **Access**: User
- **Parameters**:
  - `file`: Filename to preview
- **Response**: HTML file preview
- **Description**: Preview USB file

### Fan Control

#### Turn On Fan
- **URL**: `GET /fan/on`
- **Access**: User
- **Response**: JSON confirmation
- **Description**: Turn on cooling fan

#### Turn Off Fan
- **URL**: `GET /fan/off`
- **Access**: User
- **Response**: JSON confirmation
- **Description**: Turn off cooling fan

## Response Formats

### Success Response
```json
{
  "success": true,
  "message": "Operation completed successfully",
  "data": {}
}
```

### Error Response
```json
{
  "error": "Error description",
  "code": 400,
  "message": "Bad Request"
}
```

### Printer Status Response
```json
{
  "status": "idle",
  "plateID": "12345",
  "layer": 150,
  "totalLayers": 200,
  "progress": 75.5,
  "timeElapsed": "2h 30m",
  "timeLeft": "45m",
  "temperature": 25.5,
  "build": "1.43.0",
  "cast": false,
  "panicked": false,
  "lastUpdate": "2023-08-08T10:00:00Z"
}
```

### Slicer Status Response
```json
{
  "status": "idle",
  "progress": 75.5,
  "currentJob": "plate_12345",
  "queueSize": 3
}
```

### Task Progress Response
```json
{
  "id": "task_12345",
  "status": "running",
  "progress": 75.5,
  "percentage": "75",
  "text": "Processing layer 150 of 200"
}
```

## Error Codes

- **200**: Success
- **400**: Bad Request
- **401**: Unauthorized
- **403**: Forbidden
- **404**: Not Found
- **500**: Internal Server Error

## Rate Limiting

The API implements rate limiting to prevent abuse. Respect reasonable request rates and implement exponential backoff for retries.

## Best Practices

### Authentication
- Store tokens securely
- Rotate tokens regularly
- Use HTTPS in production
- Implement proper error handling

### Error Handling
- Always check response status
- Implement retry logic with backoff
- Log errors for debugging
- Handle network timeouts gracefully

### Performance
- Cache frequently accessed data
- Use pagination for large datasets
- Implement request batching when possible
- Monitor API usage and performance

## SDK and Libraries

### Official Libraries
- **Python**: `nanodlp-python` (planned)
- **JavaScript**: `nanodlp-js` (planned)
- **Go**: Native Go support

### Community Libraries
- Check community repositories for unofficial libraries
- Ensure compatibility with your NanoDLP version
- Test thoroughly before production use

## Related Topics

- [Web Interface]({{<ref "web-interface">}})
- [Machine Configuration]({{<ref "machine-configuration">}})
- [Profile Management]({{<ref "profiles">}})
- [Hardware Management]({{<ref "hardware-management">}})

---
title: "Profile Management"
description: "Complete guide to NanoDLP profile settings and configuration options for optimal 3D printing results."
lead: "Learn how to configure and manage print profiles for different resins and materials in NanoDLP."
draft: false
menu:
  docs:
    parent: "manual"
images: []
toc: true
---

## Overview

NanoDLP profiles allow you to create and manage different print configurations for various resins and materials. Each profile contains settings that can override machine-level configurations and are optimized for specific printing scenarios.

## Profile Types

### Resin Profiles
Standard profiles for UV-curable resins with customizable exposure and movement parameters.

### Wash Profiles
Specialized profiles for cleaning and post-processing operations.

## Basic Profile Settings

### General Information
- **Title**: Descriptive name for the profile
- **Description**: Detailed description of the profile's purpose
- **Color**: Visual color representation for easy identification
- **Resin Price**: Cost tracking for material management
- **Optimum Temperature**: Recommended operating temperature for the resin

### Support Configuration
- **Support Top Wait**: Wait time after support layer completion
- **Support Wait Height**: Height at which support wait begins
- **Support Depth**: Depth of support structures
- **Support Wait Before/After Print**: Timing controls for support operations
- **Support Layer Number**: Number of layers to apply support settings

## User-Defined Settings

### Movement Parameters
- **Z Step Wait**: Z-axis movement speed control
- **Lift Speed**: Speed of platform lifting between layers
- **Retract Speed**: Speed of platform lowering to next layer

### Timing Controls
- **Top Wait**: Wait time at the top of each layer
- **Wait Height**: Height at which wait operations begin
- **Cure Time**: Exposure duration for each layer
- **Wait Before/After Print**: Pre and post-print timing

### Support-Specific Settings
- **Support Cure Time**: Special exposure time for support layers
- **Support Layer Number**: Number of layers to apply support settings

## Code Options

### Dynamic Controls
- **Dynamic Cure Time**: Custom G-code for variable exposure times
- **Dynamic Speed**: Custom G-code for variable movement speeds
- **Dynamic Retract Speed**: Custom G-code for variable retraction speeds

### Shield Integration
- **Shield Before Layer**: G-code executed before layer display
- **Shield After Layer**: G-code executed after layer display
- **Shield During Cure**: G-code executed during curing process
- **Shield Start**: G-code for shield initialization
- **Shield Resume**: G-code for shield resumption
- **Shield Finish**: G-code for shield completion

### Specialized Controls
- **Laser Code**: Custom G-code for laser-based printers
- **Shutter Open/Close Gcode**: G-code for mechanical shutter control

## Detection and Safety

### Detection Systems
- **Separation Detection**: Layer separation monitoring
- **Resin Level Detection**: Material level monitoring
- **Auto Level Detection**: Automatic leveling system
- **Crash Detection**: Collision detection and prevention
- **Dynamic Wait**: Adaptive wait timing based on conditions

## Advanced Slicing Options

### Adaptive Features
- **Adapt Slicing**: Enable adaptive layer thickness
- **Adapt Slicing Min/Max**: Layer thickness boundaries
- **Support Offset**: Support structure positioning
- **Offset**: General positioning adjustments

### Erode Configuration
- **Erode Start Mode**: When to begin erode operations
  - 0: Immediate after support
  - 1: After X layers
  - 2: After Z mm height
- **Erode Start Layer**: Specific layer number for erode start
- **Erode Start Height**: Z-height for erode initiation

### Visual Enhancements
- **Fill Color**: Color for filled areas
- **Blank Color**: Color for blank/empty areas
- **Dim Amount**: Dimming intensity
- **Dim Wall**: Wall dimming settings
- **Dim Border**: Border dimming configuration
- **Dim Skip**: Skip patterns for dimming
- **Pixel Diming**: Per-pixel dimming control

### Hatching and Patterns
- **Hatching Type**: Pattern type for hatching
- **Hatching Wall**: Wall thickness for hatching
- **Hatching Gap**: Gap between hatching lines
- **Hatching Outer Wall**: Outer wall hatching settings
- **Hatching Top/Bottom Cap**: Top and bottom layer patterns
- **Hatching Border**: Border hatching configuration
- **Hatching Space**: Spacing between hatching elements
- **Hatching Outer**: Outer area hatching settings

### Quality Improvements
- **Multi Cure Gap**: Gap for multi-cure operations
- **Anti-Alias Threshold**: Anti-aliasing sensitivity
- **Anti-Alias**: Standard anti-aliasing control
- **Anti-Alias 3D**: 3D anti-aliasing settings
- **Image Rotate**: Image rotation control
- **Ignore Mask**: Mask ignoring options

## Resolution and Scaling

### Resolution Control
- **XY Resolution**: X and Y axis resolution
- **Y Resolution**: Y-axis specific resolution
- **Z Resolution Percentage**: Z-axis resolution scaling

### Shrinkage Compensation
- **X Scale**: X-axis scaling for resin shrinkage
- **Y Scale**: Y-axis scaling for resin shrinkage
- **Z Scale**: Z-axis scaling for resin shrinkage

## Advanced Features

### Extended EFME (Elephant Foot Mitigation Enhanced)
- **EFME Mode**: Application mode selection
  - 0: Burn-in only
  - 1: All layers
  - 2: Selected layers
- **EFME Max Layer**: Maximum layer for EFME application
- **EFME Continuous**: Continuous timing mode
- **EFME Guard Band**: Guard band thickness

### Elephant Foot Mitigation
- **Elephant Type**: Mitigation method selection
- **Elephant Amount**: Mitigation intensity
- **Elephant Wall**: Wall thickness settings
- **Elephant Border**: Border configuration
- **Elephant Thickness**: Thickness parameters
- **Elephant Layers**: Layer count for mitigation

### Ring Exposure System
- **Ring Exposure Enabled**: Enable/disable ring exposure
- **Ring Thickness**: Thickness of exposure ring
- **Ring Exposure Reduction**: Exposure reduction percentage
- **Ring Gradient Falloff**: Gradient falloff control
- **Ring Exposure Mode**: Application mode selection
- **Ring Max Layer**: Maximum layer for ring exposure

### Advanced Base Layer
- **Advanced Base Layer**: Enable/disable advanced base layer
- **Base Layer Seed Size**: Initial exposure dot size
- **Base Layer Seed Spacing**: Spacing between seed dots
- **Base Layer Seed Exposure**: Seed stage exposure time
- **Base Layer Lattice Exposure**: Lattice stage exposure time
- **Base Layer Final Exposure**: Final stage exposure time
- **Base Layer Max Layers**: Maximum layers for advanced base layer

## Direct Control

### Slow Section Control
- **Slow Section Height**: Height for slow movement sections
- **Slow Section Step Wait**: Wait time in slow sections

## Profile Management

### Creating Profiles
1. Navigate to the Profile Management section
2. Click "Add New Profile"
3. Configure basic settings and parameters
4. Save the profile with a descriptive name

### Editing Profiles
1. Select the profile to edit
2. Modify desired parameters
3. Save changes (note: some changes require plate regeneration)

### Profile Organization
- Use descriptive names and descriptions
- Group profiles by resin type or application
- Maintain consistent naming conventions
- Document special settings or requirements

## Best Practices

### Profile Optimization
- Start with manufacturer-recommended settings
- Test with small calibration prints
- Document successful configurations
- Use profiles for different resin batches

### Safety Considerations
- Always test new profiles with small prints
- Monitor print quality and adhesion
- Adjust exposure times gradually
- Keep backup profiles for known good settings

## Related Topics

- [Machine Configuration]({{<ref "settings">}})
- [Print Quality]({{<ref "print-quality">}})
- [Elephant Foot Mitigation]({{<ref "elephant-foot">}})
- [Dimming]({{<ref "dimming">}})
- [Erode]({{<ref "erode">}})
- [Hollowing]({{<ref "hollowing">}})

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

NanoDLP profiles allow you to create and manage different print configurations for various resins and materials. Each profile contains settings that can override machine-level configurations and are optimized for specific printing scenarios. This guide focuses on practical profile creation and management rather than just listing parameters.

## Why Profiles Matter

Profiles are essential because:
- **Different resins need different settings** for optimal results
- **Consistent quality** across multiple prints
- **Time savings** from not reconfiguring settings
- **Material optimization** for cost and quality
- **Team collaboration** with shared configurations

## Creating Your First Profile

### Step 1: Start with a Base Profile
1. Go to **Profiles** in the main menu
2. Click **Add Profile** or duplicate an existing profile
3. Give it a descriptive name (e.g., "Standard Resin - 0.05mm")
4. Choose a distinctive color for easy identification

### Step 2: Configure Essential Settings
Start with these critical parameters that affect print quality:

#### Basic Print Settings
- **Cure Time**: Start with 8-12 seconds for standard resins
- **Lift Speed**: 60-100 mm/min for most printers
- **Retract Speed**: 150-300 mm/min for faster printing
- **Z Step Wait**: 0.5-1 second between movements

#### Support Settings
- **Support Cure Time**: Usually 1.5-2x normal cure time
- **Support Top Wait**: 2-5 seconds for proper adhesion
- **Support Wait Height**: 1-2 mm above the build platform

### Step 3: Test and Refine
1. Print a small calibration model
2. Check layer adhesion and surface quality
3. Adjust cure time if layers don't stick properly
4. Fine-tune speeds if you experience issues

## Profile Types and Use Cases

### Standard Resin Profiles
**Best for**: General-purpose printing, prototypes, functional parts

**Typical Settings**:
- **Cure Time**: 8-12 seconds
- **Lift Speed**: 80 mm/min
- **Layer Height**: 0.05-0.1 mm
- **Support Settings**: Standard support configuration

**When to Use**:
- First-time setup
- General prototyping
- Learning and experimentation
- Most standard resins

### High-Detail Profiles
**Best for**: Miniatures, detailed models, display pieces

**Typical Settings**:
- **Cure Time**: 10-15 seconds
- **Lift Speed**: 60 mm/min
- **Layer Height**: 0.025-0.05 mm
- **Anti-Aliasing**: Enabled
- **Multi-Cure**: 2-3 passes

**When to Use**:
- High-detail requirements
- Small, intricate models
- Display-quality prints
- Professional applications

### Fast Production Profiles
**Best for**: Batch printing, rapid prototyping, functional testing

**Typical Settings**:
- **Cure Time**: 6-8 seconds
- **Lift Speed**: 100-150 mm/min
- **Layer Height**: 0.075-0.1 mm
- **Anti-Aliasing**: Disabled (for speed)
- **Multi-Cure**: 1-2 passes

**When to Use**:
- Quick iterations
- Functional testing
- Batch production
- Time-sensitive projects

### Specialty Material Profiles
**Best for**: Flexible resins, high-temperature materials, specialty applications

**Typical Settings**:
- **Cure Time**: 15-25 seconds (material-dependent)
- **Lift Speed**: 40-60 mm/min (slower for delicate materials)
- **Layer Height**: 0.05-0.075 mm
- **Multi-Cure**: 3-4 passes
- **Special handling**: May need custom G-code

**When to Use**:
- Flexible or specialty resins
- High-temperature applications
- Medical or food-safe materials
- Experimental materials

## Essential Profile Settings Explained

### Cure Time: The Foundation
**What it does**: Controls how long each layer is exposed to UV light

**How to set it**:
- **Start conservative**: Begin with manufacturer recommendations
- **Test with calibration**: Use a small test print to verify
- **Adjust based on results**: Increase if layers don't stick, decrease if over-cured
- **Consider layer height**: Thicker layers may need longer cure times

**Common values**:
- **Fast resins**: 6-8 seconds
- **Standard resins**: 8-12 seconds
- **Slow resins**: 12-18 seconds
- **Specialty resins**: 15-25 seconds

### Movement Settings: Speed and Reliability
**Lift Speed**: How fast the platform moves up between layers
- **Too fast**: May cause layer separation
- **Too slow**: Increases print time unnecessarily
- **Sweet spot**: 60-100 mm/min for most applications

**Retract Speed**: How fast the platform moves down to the next layer
- **Can be faster**: Usually 2-3x lift speed
- **Consider resin viscosity**: Thicker resins may need slower retraction

**Z Step Wait**: Pause between movements
- **Purpose**: Allows resin to settle and bubbles to escape
- **Too short**: May cause air bubbles or poor adhesion
- **Too long**: Unnecessary delays

### Support Configuration: Building Success
**Support Cure Time**: Exposure time for support structures
- **Usually longer**: 1.5-2x normal cure time
- **Purpose**: Ensures supports are strong enough
- **Too short**: Weak supports may fail
- **Too long**: Over-cured supports are hard to remove

**Support Wait Height**: When support settings take effect
- **Start early**: Begin 1-2 mm above the build platform
- **Consider model**: Complex models may need earlier support

## Advanced Profile Features

### Multi-Cure: Enhanced Quality
**What it does**: Performs multiple curing passes per layer

**When to use**:
- **Quality requirements**: High-detail or professional prints
- **Difficult materials**: Resins that need extra curing
- **Complex geometries**: Models with challenging features

**Configuration**:
- **Start with 2 passes**: Most materials benefit from this
- **Increase if needed**: Up to 4 passes for difficult materials
- **Monitor time**: Each pass adds time per layer

### Anti-Aliasing: Smooth Surfaces
**What it does**: Smooths edges and reduces stair-stepping

**When to use**:
- **Curved surfaces**: Models with lots of curves
- **High quality**: When surface finish matters
- **Display models**: Parts that will be visible

**Configuration**:
- **Enable for quality**: Set to 1 for smooth surfaces
- **Adjust threshold**: Lower values = smoother but slower
- **Test first**: Verify quality improvement vs. time cost

### Adaptive Slicing: Smart Layer Thickness
**What it does**: Automatically adjusts layer thickness based on geometry

**When to use**:
- **Mixed complexity**: Models with both simple and complex areas
- **Time optimization**: Faster printing of simple areas
- **Quality optimization**: Better detail in complex areas

**Configuration**:
- **Enable**: Set Adapt Slicing to 1
- **Set range**: Min 0.025mm, Max 0.1mm (start conservative)
- **Test transitions**: Ensure smooth transitions between thicknesses

## Profile Management Best Practices

### Organization Strategy
1. **Use descriptive names**: Include resin type, layer height, and purpose
2. **Color coding**: Assign colors for quick visual identification
3. **Group by material**: Organize profiles by resin type
4. **Version control**: Keep track of successful configurations

### Testing and Validation
1. **Start small**: Test new profiles with calibration models
2. **Document results**: Keep notes on what works and what doesn't
3. **Iterate gradually**: Make small changes and test each one
4. **Validate with real models**: Test with your actual use cases

### Maintenance and Updates
1. **Regular review**: Periodically review and update profiles
2. **Material changes**: Update profiles when switching resins
3. **Seasonal adjustments**: Consider temperature and humidity changes
4. **Backup profiles**: Export and backup successful configurations

## Troubleshooting Profile Issues

### Common Problems and Solutions

#### Poor Layer Adhesion
**Symptoms**: Layers separating, weak prints
**Solutions**:
- Increase cure time by 1-2 seconds
- Check resin temperature (should be 20-25°C)
- Verify layer height isn't too thick
- Ensure proper support configuration

#### Over-Curing
**Symptoms**: Brittle prints, rough surfaces, hard to remove supports
**Solutions**:
- Decrease cure time by 1-2 seconds
- Reduce multi-cure passes
- Check UV light intensity
- Verify resin isn't expired

#### Print Failures
**Symptoms**: Complete print failures, stuck to FEP
**Solutions**:
- Check lift speed (may be too fast)
- Verify Z step wait (may be too short)
- Ensure proper support configuration
- Check resin level and viscosity

#### Slow Printing
**Symptoms**: Unnecessarily long print times
**Solutions**:
- Increase lift and retract speeds
- Reduce Z step wait time
- Optimize layer height
- Consider adaptive slicing

## Profile Templates and Sharing

### Creating Templates
1. **Start with a working profile**: Use a profile that works well
2. **Remove specific settings**: Clear resin-specific parameters
3. **Add documentation**: Include usage notes and recommendations
4. **Test thoroughly**: Verify template works with different materials

### Sharing Profiles
1. **Export profiles**: Use NanoDLP's export functionality
2. **Document settings**: Include material recommendations
3. **Share best practices**: Include tips for successful use
4. **Version control**: Keep track of profile versions

## Next Steps

Once you're comfortable with profile management:
- **[Advanced Slicing]({{<ref "advanced-slicing">}})** - Fine-tune slicing for optimal results
- **[Machine Configuration]({{<ref "machine-configuration">}})** - Optimize hardware settings
- **[Print Quality]({{<ref "print-quality">}})** - Monitor and improve results
- **[Job Management]({{<ref "job-management">}})** - Efficiently manage multiple prints

## Related Topics

- [Advanced Slicing]({{<ref "advanced-slicing">}}) - Fine-tune slicing parameters
- [Machine Configuration]({{<ref "machine-configuration">}}) - Hardware setup and calibration
- [Print Quality]({{<ref "print-quality">}}) - Monitor and improve results
- [Job Management]({{<ref "job-management">}}) - Manage print jobs efficiently

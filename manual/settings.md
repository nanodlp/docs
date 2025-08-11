---
title: "Settings Overview"
description: "Overview of NanoDLP configuration options and settings categories for optimal printer performance."
lead: "There are many settings and parameters that could be used to setup your printer on NanoDLP. Here we go through overview of those settings."
draft: false
menu:
  docs:
    parent: "manual"
images: []
toc: true
---

## Overview

There are two main categories of settings in NanoDLP that work together to control your printer's behavior and performance. Understanding how these settings interact is crucial for achieving optimal print quality and reliability.

## Settings Categories

### Machine Settings

Machine settings contain general parameters that define how your printer hardware should operate. These are fundamental configurations that affect the entire printing system.

**Key Machine Settings Include:**
- Hardware pin assignments and configurations
- Motor characteristics and movement parameters
- Display and projector configurations
- Network and communication settings
- System-level parameters

**For detailed machine configuration, see:**
- **[Machine Configuration]({{<ref "machine-configuration">}})** - Complete guide to all machine settings
- **[Hardware Setup]({{<ref "hardware">}})** - Hardware installation and configuration
- **[Hardware Management]({{<ref "hardware-management">}})** - Hardware control and monitoring

### Profile Settings

Profile settings allow you to define multiple print configurations optimized for different resins and materials. Profile settings can override machine-level configurations and are essential for material-specific optimization.

**Key Profile Settings Include:**
- Resin-specific exposure parameters
- Movement and timing controls
- Advanced slicing options
- Quality enhancement features
- Material-specific calibrations

**For detailed profile configuration, see:**
- **[Profile Management]({{<ref "profiles">}})** - Complete guide to profile settings
- **[Advanced Slicing]({{<ref "advanced-slicing">}})** - Advanced slicing features
- **[Print Quality]({{<ref "print-quality">}})** - Quality optimization techniques

## Configuration Interfaces

### Web Interface

The web interface provides user-friendly access to all settings through an intuitive browser-based interface.

**Web Interface Features:**
- Visual configuration panels
- Real-time parameter updates
- Integrated help and documentation
- Mobile-responsive design
- Multi-language support

**For web interface details, see:**
- **[Web Interface]({{<ref "web-interface">}})** - Complete web interface guide
- **[API Reference]({{<ref "api-reference">}})** - Programmatic access to settings

### Programmatic Access

For advanced users and automation, NanoDLP provides comprehensive API access to all settings.

**API Features:**
- REST API endpoints for all functions
- JSON-based configuration management
- Secure authentication and authorization
- Real-time status monitoring
- Automated configuration management

## Setting Indicators

NanoDLP uses visual indicators to help you understand the impact and requirements of different settings.

### Help ℹ

Links to on-screen help or documentation containing detailed information about specific settings.

**When you see this icon:**
- Click for detailed explanations
- Review related documentation
- Understand parameter relationships
- Learn best practices

### Caution 🔥

These settings may seem innocent but can cause various issues if configured incorrectly. It's better to understand them thoroughly before making changes.

**Caution settings typically include:**
- Hardware pin assignments
- Motor speed and acceleration
- Exposure timing parameters
- Safety-related configurations

**Best practices:**
- Research before changing
- Test with small prints first
- Document your changes
- Have backup configurations ready

### Formula ∑

On-screen formula calculators help you see how changes to these inputs impact your prints in real-time.

**Formula features:**
- Real-time calculation updates
- Parameter relationship visualization
- Print time and material estimates
- Quality impact predictions

### Regenerate ⟲

Changes to most NanoDLP options are applied on-the-fly, meaning you can change parameters during printing and see results immediately. However, some parameters require re-slicing and plate regeneration.

**On-the-fly changes include:**
- Exposure times
- Movement speeds
- Wait times
- Basic timing parameters

**Regeneration-required changes include:**
- Resolution settings
- Slicing algorithms
- Advanced features
- Geometry modifications

## Printer Types

NanoDLP supports different printer types, each with different properties and behaviors.

### Projector / LCD

This is the default printer type and the only one that currently supports direct control. All settings function as intended for shield control.

**Key Features:**
- Full feature support
- Shield integration
- Direct control capabilities
- Advanced slicing options

**When using custom curing code instead of NanoDLP's default:**
The shield itself takes over cure time management. Each layer is displayed entirely before the shield activates the UV LED to cure it. This approach is ideal for fast, high-resolution printers (8k+).

**Example custom curing code:**
```
[[MoveCounterSet 0]]
G1 Z1; Move to layer
M104; UV LED On
G4 P1400; Cure layer
M105; UV LED Off
[[MoveWait 2]]; Both G1 and G2 returns Z_move_comp
```

### Laser

If you're using a galvo laser type printer for SLA or SLS, this is the printer type you need to choose. Instead of curing layers, it generates G-code for the shield to move the laser source in the X/Y plane.

**Laser-specific features:**
- G-code generation for laser movement
- Laser power control
- Scanning pattern optimization
- Laser-specific safety features

## Advanced Configuration

### Custom Values

NanoDLP supports custom configuration values for advanced users who need specialized settings not covered by standard parameters.

**Custom value applications:**
- Specialized hardware configurations
- Custom G-code sequences
- External system integrations
- Experimental features

### Integration Settings

Configure how NanoDLP integrates with external systems and services.

**Integration options:**
- Remote slicing services
- External monitoring systems
- Automation platforms
- Cloud services

## Best Practices

### Configuration Strategy

1. **Start with defaults**: Begin with manufacturer-recommended settings
2. **Test incrementally**: Make small changes and test thoroughly
3. **Document changes**: Keep records of all configuration modifications
4. **Backup regularly**: Create backups before major changes
5. **Monitor performance**: Track how changes affect print quality

### Safety Considerations

1. **Understand parameters**: Research settings before changing them
2. **Test safely**: Use small test prints for new configurations
3. **Monitor operation**: Watch for unusual behavior after changes
4. **Have fallbacks**: Keep known-good configurations as backups
5. **Follow guidelines**: Adhere to manufacturer recommendations

### Performance Optimization

1. **Balance quality and speed**: Find optimal settings for your needs
2. **Material optimization**: Adjust settings for specific resins
3. **Hardware utilization**: Maximize your printer's capabilities
4. **Efficiency improvements**: Reduce waste and improve reliability

## Troubleshooting

### Common Configuration Issues

- **Parameter conflicts**: Check for conflicting settings
- **Hardware mismatches**: Verify hardware compatibility
- **Performance degradation**: Monitor for quality issues
- **System instability**: Watch for crashes or errors

### Getting Help

- Use the built-in help system
- Consult the comprehensive documentation
- Check community forums and support
- Review troubleshooting guides

## Related Topics

- **[Machine Configuration]({{<ref "machine-configuration">}})** - Detailed machine settings guide
- **[Profile Management]({{<ref "profiles">}})** - Profile configuration guide
- **[Web Interface]({{<ref "web-interface">}})** - Web interface usage guide
- **[API Reference]({{<ref "api-reference">}})** - Programmatic configuration
- **[Hardware Management]({{<ref "hardware-management">}})** - Hardware configuration
- **[Advanced Slicing]({{<ref "advanced-slicing">}})** - Advanced feature configuration
- **[Speed]({{<ref "speed">}})** - Speed optimization settings
- **[Display Calibration]({{<ref "display-calibration">}})** - Display configuration

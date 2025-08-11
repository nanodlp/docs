---
title: "Advanced Slicing"
description: "Complete guide to NanoDLP's advanced slicing features, adaptive slicing, and quality optimization techniques."
lead: "Learn how to use advanced slicing features to achieve optimal print quality and performance."
draft: false
menu:
  docs:
    parent: "manual"
images: []
toc: true
---

## Overview

NanoDLP's advanced slicing features provide sophisticated control over the printing process, allowing you to optimize print quality, reduce material usage, and achieve better results with complex geometries. These features go beyond basic slicing to provide intelligent, adaptive printing solutions.

## Adaptive Slicing

### Overview
Adaptive slicing automatically adjusts layer thickness based on model geometry, providing optimal resolution where needed while maintaining efficiency in simpler areas.

### Configuration
- **Adapt Slicing**: Enable/disable adaptive slicing (0=disabled, 1=enabled)
- **Adapt Slicing Min**: Minimum layer thickness in millimeters
- **Adapt Slicing Max**: Maximum layer thickness in millimeters

### Benefits
- **Quality Improvement**: Better detail in complex areas
- **Time Reduction**: Faster printing in simple areas
- **Material Efficiency**: Optimized layer thickness
- **Surface Quality**: Smoother surfaces on curved areas

### Best Practices
- Start with conservative min/max values
- Monitor print quality in transition areas
- Adjust based on model complexity
- Test with calibration models first

## Erode Configuration

### Overview
Erode operations create internal cavities and reduce material usage while maintaining structural integrity. This feature is essential for creating lightweight, efficient prints.

### Start Configuration
- **Erode Start Mode**: Control when erode begins
  - 0: Immediate after support layers
  - 1: After specified number of layers
  - 2: After specified Z height
- **Erode Start Layer**: Layer number to start erode (mode 1)
- **Erode Start Height**: Z height in mm to start erode (mode 2)

### Applications
- **Hollowing**: Create internal cavities
- **Material Reduction**: Reduce resin consumption
- **Structural Optimization**: Maintain strength while reducing weight
- **Support Integration**: Coordinate with support structures

### Configuration Tips
- Start erode after sufficient base layers
- Consider model geometry for start timing
- Balance material savings with structural integrity
- Test with small prints before full-scale use

## Visual Enhancement Features

### Color Management
- **Fill Color**: Color for filled/solid areas
- **Blank Color**: Color for empty/void areas
- **Color Customization**: RGB color selection
- **Visual Feedback**: Real-time color preview

### Dimming Controls
- **Dim Amount**: Overall dimming intensity (0-100%)
- **Dim Wall**: Wall thickness for dimming effects
- **Dim Border**: Border dimming configuration
- **Dim Skip**: Skip patterns for dimming
- **Pixel Diming**: Per-pixel dimming control

### Applications
- **Surface Quality**: Improve surface finish
- **Detail Enhancement**: Enhance fine features
- **Visual Appeal**: Create aesthetic effects
- **Quality Control**: Monitor print progress

## Hatching and Pattern Systems

### Hatching Types
- **Standard Hatching**: Traditional infill patterns
- **Advanced Hatching**: Custom pattern generation
- **Adaptive Hatching**: Geometry-based pattern selection
- **Custom Hatching**: User-defined patterns

### Hatching Configuration
- **Hatching Wall**: Wall thickness for hatching
- **Hatching Gap**: Gap between hatching lines
- **Hatching Outer Wall**: Outer wall hatching settings
- **Hatching Top Cap**: Top layer pattern
- **Hatching Bottom Cap**: Bottom layer pattern
- **Hatching Border**: Border area hatching
- **Hatching Space**: Spacing between elements
- **Hatching Outer**: Outer area patterns

### Pattern Optimization
- **Strength vs. Speed**: Balance structural integrity with print time
- **Material Usage**: Optimize infill density
- **Surface Quality**: Improve top and bottom surfaces
- **Support Integration**: Coordinate with support structures

## Anti-Aliasing and Quality

### Anti-Aliasing Features
- **Standard Anti-Alias**: Basic edge smoothing
- **Anti-Alias 3D**: Three-dimensional smoothing
- **Anti-Alias Threshold**: Sensitivity control
- **Quality vs. Performance**: Balance smoothness with speed

### Image Processing
- **Image Rotate**: Rotate images for optimal orientation
- **Ignore Mask**: Selective mask processing
- **Quality Filters**: Apply quality enhancement filters
- **Resolution Optimization**: Maximize effective resolution

## Multi-Cure Operations

### Multi-Cure Configuration
- **Multi Cure Gap**: Gap between multi-cure passes
- **Cure Passes**: Number of curing passes per layer
- **Pass Timing**: Timing between passes
- **Quality Enhancement**: Improve layer adhesion

### Applications
- **High-Quality Prints**: Enhanced surface finish
- **Difficult Materials**: Better adhesion for challenging resins
- **Complex Geometries**: Improved detail reproduction
- **Production Quality**: Professional-grade results

## Advanced Base Layer Features

### Multi-Stage Exposure
- **Seed Stage**: Initial exposure dots
- **Lattice Stage**: Intermediate structure formation
- **Final Stage**: Complete layer curing
- **Stage Timing**: Exposure time for each stage

### Configuration
- **Base Layer Seed Size**: Size of initial exposure dots
- **Base Layer Seed Spacing**: Spacing between seeds
- **Base Layer Seed Exposure**: Seed stage exposure time
- **Base Layer Lattice Exposure**: Lattice stage exposure time
- **Base Layer Final Exposure**: Final stage exposure time
- **Base Layer Max Layers**: Maximum layers for advanced base layer

### Benefits
- **Warping Reduction**: Minimize print warping
- **Adhesion Improvement**: Better platform adhesion
- **Surface Quality**: Smoother base surfaces
- **Reliability**: More consistent first layers

## Ring Exposure System

### Overview
The Ring Exposure System provides single-exposure elephant foot mitigation by creating exposure rings around layer edges.

### Configuration
- **Ring Exposure Enabled**: Enable/disable ring exposure
- **Ring Thickness**: Thickness of exposure ring in mm
- **Ring Exposure Reduction**: Exposure reduction percentage (0-100%)
- **Ring Gradient Falloff**: Enable gradient falloff (0=binary, 1=gradient)
- **Ring Exposure Mode**: Application mode selection
  - 0: Burn-in layers only
  - 1: All layers
  - 2: Selected layers
- **Ring Max Layer**: Maximum layer for ring exposure (mode 2)

### Applications
- **Elephant Foot Mitigation**: Reduce base layer expansion
- **Dimensional Accuracy**: Improve print dimensions
- **Surface Quality**: Better surface finish
- **Support Integration**: Coordinate with support structures

## EFME (Elephant Foot Mitigation Enhanced)

### Overview
Extended EFME provides advanced elephant foot mitigation with multiple application modes and continuous operation options.

### Configuration
- **EFME Mode**: Application mode selection
  - 0: Burn-in layers only
  - 1: All layers
  - 2: Selected layers
- **EFME Max Layer**: Maximum layer for EFME application
- **EFME Continuous**: Continuous/near-continuous timing
- **EFME Guard Band**: Guard band thickness in mm

### Advanced Features
- **Continuous Operation**: Near-continuous exposure timing
- **Guard Band Protection**: Protective exposure zones
- **Selective Application**: Layer-specific application
- **Quality Optimization**: Enhanced mitigation effectiveness

## Resolution and Scaling

### Resolution Control
- **XY Resolution**: X and Y axis resolution control
- **Y Resolution**: Y-axis specific resolution
- **Z Resolution Percentage**: Z-axis resolution scaling
- **Dynamic Resolution**: Adaptive resolution adjustment

### Shrinkage Compensation
- **X Scale**: X-axis scaling for resin shrinkage
- **Y Scale**: Y-axis scaling for resin shrinkage
- **Z Scale**: Z-axis scaling for resin shrinkage
- **Material-Specific Scaling**: Resin-dependent compensation

### Calibration
- **Resolution Calibration**: Accurate resolution measurement
- **Scale Calibration**: Precise scaling factors
- **Material Testing**: Resin-specific calibration
- **Quality Verification**: Print quality validation

## Quality Optimization

### Print Quality Factors
- **Layer Adhesion**: Ensure proper layer bonding
- **Surface Finish**: Optimize surface quality
- **Dimensional Accuracy**: Maintain print dimensions
- **Detail Reproduction**: Preserve fine features

### Optimization Techniques
- **Parameter Tuning**: Fine-tune slicing parameters
- **Material Testing**: Test with different resins
- **Geometry Analysis**: Analyze model complexity
- **Quality Monitoring**: Track print quality metrics

## Best Practices

### Configuration Strategy
- Start with conservative settings
- Test with calibration models
- Document successful configurations
- Gradually optimize parameters

### Quality Control
- Monitor print quality consistently
- Use quality assessment tools
- Track parameter changes
- Maintain quality standards

### Performance Optimization
- Balance quality with speed
- Optimize for specific materials
- Consider production requirements
- Monitor system performance

## Troubleshooting

### Common Issues
- **Poor Surface Quality**: Check anti-aliasing and dimming settings
- **Layer Adhesion Problems**: Verify multi-cure and base layer settings
- **Dimensional Inaccuracy**: Calibrate resolution and scaling
- **Print Failures**: Review adaptive slicing parameters

### Debug Tools
- **Layer Preview**: Examine individual layers
- **Quality Metrics**: Monitor print quality
- **Parameter Logs**: Track setting changes
- **Performance Monitoring**: Monitor system performance

## Related Topics

- [Profile Management]({{<ref "profiles">}})
- [Machine Configuration]({{<ref "machine-configuration">}})
- [Print Quality]({{<ref "print-quality">}})
- [Elephant Foot Mitigation]({{<ref "elephant-foot">}})
- [Dimming]({{<ref "dimming">}})
- [Erode]({{<ref "erode">}})
- [Hollowing]({{<ref "hollowing">}})

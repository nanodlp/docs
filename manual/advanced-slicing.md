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

NanoDLP's advanced slicing features provide sophisticated control over the printing process, allowing you to optimize print quality, reduce material usage, and achieve better results with complex geometries. This guide focuses on practical usage and real-world benefits rather than just listing parameters.

## When to Use Advanced Slicing

Advanced slicing features are most beneficial when:
- **Printing complex models** with varying detail levels
- **Optimizing for specific materials** that need special handling
- **Reducing material costs** through intelligent hollowing
- **Improving surface quality** on curved or detailed surfaces
- **Saving time** on large prints with simple areas

## Adaptive Slicing: Smart Layer Thickness

### What It Does
Adaptive slicing automatically adjusts layer thickness based on your model's geometry. Areas with lots of detail get thinner layers for better quality, while simple areas use thicker layers for faster printing.

### Real-World Benefits
- **Faster Printing**: Simple areas print 2-3x faster
- **Better Quality**: Complex areas maintain high detail
- **Material Efficiency**: Optimized layer thickness reduces waste
- **Smoother Surfaces**: Better quality on curved areas

### How to Configure

#### Step 1: Enable Adaptive Slicing
1. Go to **Profiles** → Select your resin profile
2. Find **Adapt Slicing** and set to **1** (enabled)
3. Set **Adapt Slicing Min** to **0.025** mm (minimum layer thickness)
4. Set **Adapt Slicing Max** to **0.1** mm (maximum layer thickness)

#### Step 2: Test and Adjust
- Start with conservative values (0.025-0.1 mm range)
- Print a test model with both simple and complex areas
- Gradually increase the max value if quality remains good
- Monitor transition areas between thick and thin layers

#### Step 3: Fine-tune for Your Models
- **Detailed Models**: Use 0.025-0.075 mm range
- **Simple Models**: Use 0.05-0.1 mm range
- **Mixed Complexity**: Use 0.025-0.1 mm range

### Troubleshooting Adaptive Slicing
- **Poor transitions**: Reduce the difference between min/max values
- **Quality issues**: Lower the maximum layer thickness
- **Slow printing**: Increase the minimum layer thickness

## Erode and Hollowing: Material Optimization

### What It Does
Erode operations create internal cavities and reduce material usage while maintaining structural integrity. This is perfect for creating lightweight, cost-effective prints.

### Real-World Benefits
- **Cost Savings**: Reduce resin usage by 30-70%
- **Faster Printing**: Less material means faster curing
- **Better Quality**: Reduced internal stress and warping
- **Lightweight Parts**: Ideal for functional prototypes

### How to Configure

#### Step 1: Choose When to Start Erode
1. **Erode Start Mode**: Choose when erode begins
   - **Mode 0**: Start immediately after support layers
   - **Mode 1**: Start after X layers (set **Erode Start Layer**)
   - **Mode 2**: Start after Z height (set **Erode Start Height**)

#### Step 2: Configure Erode Parameters
- **Erode Start Layer**: Start after 5-10 base layers for stability
- **Erode Start Height**: Start after 1-2 mm for proper adhesion
- **Wall Thickness**: Maintain 1-2 mm walls for strength

#### Step 3: Test Your Configuration
1. Print a small test model with erode enabled
2. Check wall thickness and structural integrity
3. Adjust start timing if needed
4. Scale up to larger models once satisfied

### Best Practices for Erode
- **Start conservative**: Begin with 1-2 mm walls
- **Test thoroughly**: Verify strength before production use
- **Consider geometry**: Complex models may need thicker walls
- **Balance savings**: Don't sacrifice too much strength for material savings

## Anti-Aliasing: Smooth Edge Quality

### What It Does
Anti-aliasing smooths the edges of your prints, reducing the "stair-step" effect and creating smoother, more professional-looking surfaces.

### Real-World Benefits
- **Smoother Surfaces**: Professional-quality finish
- **Better Detail**: Enhanced fine feature reproduction
- **Reduced Post-Processing**: Less sanding and finishing needed
- **Improved Aesthetics**: Better visual appeal

### How to Configure

#### Step 1: Enable Anti-Aliasing
1. Go to **Profiles** → Select your resin profile
2. Find **Anti-Alias 3D** and set to **1** (enabled)
3. Set **Anti-Alias Threshold** to **0.5** (start with default)

#### Step 2: Test and Optimize
- Print a test model with curved surfaces
- Check edge quality and smoothness
- Adjust threshold if needed (lower = smoother but slower)
- Monitor print time impact

### When to Use Anti-Aliasing
- **Curved Surfaces**: Models with lots of curves and organic shapes
- **High-Quality Prints**: When surface finish is critical
- **Display Models**: Parts that will be visible
- **Production Parts**: Professional-quality requirements

## Multi-Cure: Enhanced Layer Adhesion

### What It Does
Multi-cure performs multiple curing passes per layer, improving adhesion and surface quality, especially for difficult materials or complex geometries.

### Real-World Benefits
- **Better Adhesion**: Stronger layer bonding
- **Improved Quality**: Enhanced surface finish
- **Material Compatibility**: Better results with challenging resins
- **Reduced Failures**: More reliable printing

### How to Configure

#### Step 1: Enable Multi-Cure
1. Go to **Profiles** → Select your resin profile
2. Find **Multi Cure Gap** and set to **0.1** mm
3. Set **Cure Passes** to **2** (start with 2 passes)

#### Step 2: Optimize for Your Material
- **Standard Resins**: 2 passes usually sufficient
- **Difficult Materials**: Try 3-4 passes
- **High-Quality Requirements**: 2-3 passes
- **Fast Printing**: 1-2 passes

### Best Practices for Multi-Cure
- **Start with 2 passes**: Most materials benefit from this
- **Monitor print time**: Each pass adds time per layer
- **Test with your resin**: Different materials respond differently
- **Balance quality vs. speed**: Find the sweet spot for your needs

## Ring Exposure: Elephant Foot Prevention

### What It Does
Ring Exposure creates exposure rings around layer edges to prevent elephant foot (base layer expansion), improving dimensional accuracy and surface quality.

### Real-World Benefits
- **Accurate Dimensions**: Better dimensional precision
- **Smoother Surfaces**: Reduced base layer roughness
- **Better Fit**: Parts fit together more precisely
- **Professional Quality**: Improved overall appearance

### How to Configure

#### Step 1: Enable Ring Exposure
1. Go to **Profiles** → Select your resin profile
2. Find **Ring Exposure Enabled** and set to **1**
3. Set **Ring Thickness** to **0.5** mm
4. Set **Ring Exposure Reduction** to **50%**

#### Step 2: Choose Application Mode
- **Mode 0**: Burn-in layers only (recommended for most users)
- **Mode 1**: All layers (for maximum quality)
- **Mode 2**: Selected layers (for custom control)

### When to Use Ring Exposure
- **Precision Parts**: When dimensional accuracy is critical
- **Assembly Models**: Parts that need to fit together
- **Professional Prints**: High-quality requirements
- **All Prints**: Generally beneficial for most applications

## Practical Configuration Examples

### Example 1: High-Quality Display Model
```
Adapt Slicing: Enabled (0.025-0.075 mm)
Anti-Aliasing: Enabled (threshold 0.3)
Multi-Cure: 3 passes
Ring Exposure: Enabled (burn-in layers only)
Erode: Disabled (for solid quality)
```

### Example 2: Fast Functional Prototype
```
Adapt Slicing: Enabled (0.05-0.1 mm)
Anti-Aliasing: Disabled (for speed)
Multi-Cure: 2 passes
Ring Exposure: Enabled (burn-in layers only)
Erode: Enabled (start after 5 layers)
```

### Example 3: Material-Efficient Production
```
Adapt Slicing: Enabled (0.025-0.1 mm)
Anti-Aliasing: Enabled (threshold 0.5)
Multi-Cure: 2 passes
Ring Exposure: Enabled (all layers)
Erode: Enabled (start after 3 layers, 1.5 mm walls)
```

## Troubleshooting Common Issues

### Poor Surface Quality
- **Check anti-aliasing settings**: Ensure it's enabled and properly configured
- **Verify adaptive slicing**: Make sure layer transitions aren't too dramatic
- **Review multi-cure**: Increase passes for difficult materials

### Print Failures
- **Check erode settings**: Ensure walls aren't too thin
- **Verify start timing**: Don't start erode too early
- **Review material settings**: Ensure resin profile is correct

### Slow Printing
- **Optimize adaptive slicing**: Increase minimum layer thickness
- **Reduce multi-cure passes**: Use fewer passes if quality allows
- **Check anti-aliasing**: Higher threshold values are faster

## Next Steps

Once you're comfortable with these advanced features:
- **[Profile Management]({{<ref "profiles">}})** - Create optimized profiles for different materials
- **[Machine Configuration]({{<ref "machine-configuration">}})** - Fine-tune hardware settings
- **[Print Quality]({{<ref "print-quality">}})** - Monitor and improve print results
- **[Elephant Foot Mitigation]({{<ref "elephant-foot">}})** - Advanced techniques for perfect base layers

## Related Topics

- [Profile Management]({{<ref "profiles">}}) - Configure resin-specific settings
- [Machine Configuration]({{<ref "machine-configuration">}}) - Hardware setup and calibration
- [Print Quality]({{<ref "print-quality">}}) - Monitor and improve results
- [Elephant Foot Mitigation]({{<ref "elephant-foot">}}) - Advanced base layer techniques

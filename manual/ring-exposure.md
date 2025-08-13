---
title: "Ring Exposure"
description: "Complete guide to ring exposure systems for single-exposure elephant foot prevention in 3D resin printing with NanoDLP."
lead: "Learn how to prevent elephant foot with revolutionary single-exposure ring exposure technology for faster, professional-quality prints."
draft: false
menu:
  docs:
    parent: "manual"
images: []
toc: true
---

## What is Ring Exposure?

Ring Exposure is NanoDLP's revolutionary single-exposure elephant foot mitigation system that:

- **Prevents elephant foot** without the complexity of dual exposure
- **Maintains print speed** with single-exposure processing
- **Provides variable intensity** around layer edges
- **Offers multiple application modes** for different use cases
- **Reduces material waste** and improves dimensional accuracy

### Why Ring Exposure Matters
- **Perfect base layers** without dimensional distortion
- **Faster printing** compared to traditional EFME systems
- **Better part fit** for assembly models
- **Professional quality** with minimal post-processing
- **Consistent results** across different geometries

## How Ring Exposure Works

### Single-Exposure Technology
Unlike traditional dual-exposure systems, Ring Exposure processes images during slicing:

1. **Edge Detection**: Identifies layer boundaries
2. **Ring Creation**: Creates exposure rings around edges
3. **Intensity Reduction**: Applies graduated exposure reduction
4. **Single Exposure**: Processes everything in one exposure cycle

### Processing Modes
Ring Exposure offers three application modes:

- **Mode 0**: Burn-in layers only (recommended for most users)
- **Mode 1**: All layers (maximum quality, slower)
- **Mode 2**: Selected layers (custom control)

## Configuration Guide

### Step 1: Enable Ring Exposure
1. **Go to Profiles** → Select your resin profile
2. **Find Ring Exposure Enabled** → Set to **1**
3. **Set Ring Thickness** → Start with **0.5 mm**
4. **Set Ring Exposure Reduction** → Start with **50%**
5. **Set Ring Exposure Mode** → Use **0** (burn-in layers)

### Step 2: Advanced Configuration
- **Ring Thickness**: Controls the width of the exposure ring
- **Exposure Reduction**: Percentage of exposure reduction in ring area
- **Gradient Falloff**: Enable for smooth transitions (optional)

### Step 3: Fine-tuning
- **Too much reduction**: Parts may not stick properly
- **Too little reduction**: Elephant foot may still occur
- **Thick rings**: May affect fine details
- **Thin rings**: May not provide enough protection

## Ring Exposure vs Traditional EFME

| Feature | Ring Exposure | Traditional EFME |
|---------|---------------|------------------|
| **Exposure Cycles** | Single exposure | Dual exposure |
| **Print Speed** | Faster | Slower |
| **Complexity** | Simple | Complex |
| **Quality** | Excellent | Excellent |
| **Resource Usage** | Lower | Higher |
| **Setup Time** | Minimal | Extensive |

## Advanced Ring Exposure Features

### Gradient Falloff

#### What It Does
Gradient falloff creates smooth transitions from normal exposure to reduced exposure:

1. **Distance Calculation**: Measures distance from edge
2. **Graduated Reduction**: Applies proportional exposure reduction
3. **Smooth Transitions**: Eliminates harsh exposure boundaries
4. **Professional Quality**: Creates natural-looking edges

#### When to Use
- **High-quality prints** requiring perfect edges
- **Production parts** with strict quality requirements
- **Display models** where appearance is critical
- **Assembly parts** requiring precise fit

### Multi-Mode Operation

#### Mode 0: Burn-in Layers Only
- **Best for**: Most users and applications
- **Benefits**: Good quality, fast printing
- **Use case**: Standard printing with quality requirements

#### Mode 1: All Layers
- **Best for**: Maximum quality requirements
- **Benefits**: Perfect edges throughout the print
- **Use case**: Professional production, display models

#### Mode 2: Selected Layers
- **Best for**: Custom control requirements
- **Benefits**: Targeted quality improvement for specific areas
- **Use case**: Specific layer ranges, custom applications

## Practical Configuration Examples

### Example 1: High-Quality Display Model
```
Ring Exposure: Enabled (0.3mm, 60% reduction)
Ring Exposure Mode: 0 (burn-in layers)
Gradient Falloff: Enabled
Result: Perfect smooth surfaces, no elephant foot
```

### Example 2: Fast Functional Prototype
```
Ring Exposure: Enabled (0.7mm, 40% reduction)
Ring Exposure Mode: 0 (burn-in layers)
Gradient Falloff: Disabled
Result: Good quality with faster printing
```

### Example 3: Production Quality Parts
```
Ring Exposure: Enabled (0.4mm, 55% reduction)
Ring Exposure Mode: 1 (all layers)
Gradient Falloff: Enabled
Result: Maximum quality for production use
```

## Troubleshooting Ring Exposure

### Problem: Still Getting Elephant Foot

#### Check These Settings
1. **Ring exposure is disabled** or not properly configured
2. **Ring thickness is too thin** for your layer height
3. **Exposure reduction is too low** to be effective
4. **Base layer cure time** is still too aggressive

#### Solutions to Try
1. **Verify ring exposure is enabled** and properly configured
2. **Increase ring thickness** to 0.7-1.0mm
3. **Increase exposure reduction** to 60-70%
4. **Reduce base layer cure time** by 2-3 seconds

### Problem: Parts Not Sticking

#### Check These Settings
1. **Ring exposure reduction** is too aggressive
2. **Ring thickness is too wide** affecting adhesion
3. **Base layer cure time** is too low
4. **Build platform** is not properly prepared

#### Solutions to Try
1. **Reduce exposure reduction** to 30-40%
2. **Decrease ring thickness** to 0.3-0.5mm
3. **Increase base layer cure time** by 2-3 seconds
4. **Re-prepare build platform** surface

### Problem: Inconsistent Results

#### Check These Settings
1. **Temperature fluctuations** during printing
2. **Resin age and contamination**
3. **Profile settings** not saved properly
4. **Multiple profiles** conflicting with each other

#### Solutions to Try
1. **Stabilize room temperature** with climate control
2. **Use fresh, uncontaminated resin**
3. **Verify profile settings** are properly saved
4. **Use dedicated profiles** for specific materials

## Best Practices for Success

### 1. Start Conservative
- **Begin with mild settings** and gradually increase
- **Test with small prints** before large projects
- **Document successful configurations** for future reference
- **Don't over-optimize** - sometimes simpler is better

### 2. Consistent Environment
- **Maintain stable temperature** throughout printing
- **Avoid drafts and air currents** near your printer
- **Use consistent resin** from the same batch
- **Regular maintenance** of build platform and FEP

### 3. Systematic Testing
- **Test one variable at a time** to isolate issues
- **Use calibration models** for consistent testing
- **Measure results** with proper tools (calipers)
- **Keep detailed notes** of what works and what doesn't

### 4. Quality Over Speed
- **Don't rush** the calibration process
- **Perfect surfaces** are worth the extra time
- **Consistent quality** is more important than fast printing
- **Invest in good tools** for measurement and calibration

## Real-World Applications

### Application 1: Jewelry and Miniatures
```
Ring Exposure: Enabled (0.2mm, 70% reduction)
Layer Height: 0.025mm
Result: Perfect smooth surfaces for detailed jewelry
```

### Application 2: Engineering Prototypes
```
Ring Exposure: Enabled (0.5mm, 50% reduction)
Layer Height: 0.05mm
Result: Professional quality with good speed
```

### Application 3: Production Parts
```
Ring Exposure: Enabled (0.4mm, 55% reduction)
Layer Height: 0.04mm
Result: Consistent quality for production runs
```

## Performance Considerations

### Processing Overhead
- **Ring exposure**: Minimal impact (processed during slicing)
- **Gradient falloff**: Slight additional processing
- **Mode selection**: No performance impact
- **Overall efficiency**: Better quality with minimal processing cost

### Memory Usage
- **Ring exposure**: Minimal memory impact
- **Edge detection**: Efficient algorithms
- **Distance calculations**: Optimized for speed
- **Image processing**: Minimal memory overhead

### Print Time Impact
- **Ring exposure**: No impact on print time
- **Quality improvement**: Significant time savings in post-processing
- **Overall efficiency**: Better quality with minimal time cost
- **Processing advantage**: Single exposure maintains speed

## Choosing Between Ring Exposure and EFME

### When to Use Ring Exposure
- **Standard printing** with good quality requirements
- **Faster printing** is a priority
- **Simple setup** and configuration
- **General use** for most models and materials
- **Balanced approach** between quality and speed

### When to Use EFME
- **Maximum quality** is required
- **Professional production** environments
- **Complex geometries** with challenging edges
- **Custom control** over specific layer ranges
- **Research applications** requiring perfect dimensions

### Hybrid Approach
- **Use Ring Exposure** for standard prints
- **Enable EFME** for critical parts or specific layers
- **Test both systems** to find optimal combinations
- **Create dedicated profiles** for different quality requirements

## Next Steps

Once you've mastered ring exposure:
- **[Profile Management]({{<ref "profiles">}})** - Create optimized profiles for different materials
- **[Advanced Slicing]({{<ref "advanced-slicing">}})** - Fine-tune slicing for optimal results
- **[Print Quality]({{<ref "print-quality">}})** - Monitor and improve overall quality
- **[Machine Configuration]({{<ref "machine-configuration">}})** - Optimize hardware settings

## Related Topics

- [Anti-Wrapping (Anti-Aliasing)]({{<ref "anti-wrapping">}}) - Smooth edge quality techniques
- [Elephant Foot Mitigation]({{<ref "elephant-foot">}}) - Traditional EFME and advanced techniques
- [Profile Management]({{<ref "profiles">}}) - Configure resin-specific settings
- [Advanced Slicing]({{<ref "advanced-slicing">}}) - Fine-tune slicing parameters
- [Print Quality]({{<ref "print-quality">}}) - Monitor and improve results
- [Machine Configuration]({{<ref "machine-configuration">}}) - Hardware setup and calibration


---
title: "Elephant Foot Mitigation"
description: "Complete guide to preventing and fixing elephant foot issues in 3D resin printing with NanoDLP."
lead: "Learn how to eliminate elephant foot problems and achieve perfect base layers for professional-quality prints."
draft: false
menu:
  docs:
    parent: "manual"
images: []
toc: true
---

## What is Elephant Foot?

Elephant foot is a common 3D printing problem where the first few layers of your print are wider than intended, creating a "foot" that extends beyond the model's intended dimensions. This happens because:

- **Over-exposure** of the first layers causes resin to spread
- **Excessive adhesion** to the build platform
- **Incorrect base layer settings** that are too aggressive
- **Poor calibration** of exposure and timing

### Why It Matters
- **Dimensional accuracy** is compromised
- **Parts don't fit together** properly
- **Professional appearance** is ruined
- **Post-processing** becomes more difficult
- **Assembly issues** with multi-part models

## Prevention: The Best Approach

### 1. Proper Base Layer Configuration

#### Start with Conservative Settings
1. **Go to Profiles** → Select your resin profile
2. **Base Layer Cure Time**: Start with 15-20 seconds (not 30+ seconds)
3. **Base Layer Count**: Use 3-5 layers (not 10+ layers)
4. **Base Layer Exposure**: Match your normal layer exposure

#### Test and Adjust
1. **Print a calibration cube** (20x20x20mm)
2. **Measure the base** with calipers
3. **Adjust cure time** down if over-exposed
4. **Repeat until dimensions are correct**

### 2. Build Platform Preparation

#### Clean and Level
1. **Remove old resin** completely
2. **Clean with IPA** (isopropyl alcohol)
3. **Check leveling** with a feeler gauge
4. **Verify Z-zero** is properly set

#### Surface Treatment
1. **Light sanding** with 400-grit sandpaper
2. **Clean thoroughly** after sanding
3. **Avoid over-sanding** which can cause other issues
4. **Test adhesion** with a small print

### 3. Resin and Temperature Control

#### Optimal Conditions
- **Resin temperature**: 20-25°C (68-77°F)
- **Room temperature**: Stable, avoid drafts
- **Resin viscosity**: Not too thick or thin
- **Fresh resin**: Avoid expired or contaminated resin

#### Temperature Monitoring
1. **Use a thermometer** near your printer
2. **Monitor during printing** for temperature changes
3. **Adjust room temperature** if needed
4. **Consider a heated enclosure** for cold environments

## NanoDLP's Built-in Solutions

### Ring Exposure System

#### What It Does
Ring Exposure creates exposure rings around layer edges to prevent elephant foot by reducing exposure in critical areas while maintaining adhesion.

#### How to Configure
1. **Enable Ring Exposure**: Set to **1** (enabled)
2. **Ring Thickness**: Start with **0.5 mm**
3. **Exposure Reduction**: Start with **50%**
4. **Application Mode**: Use **Mode 0** (burn-in layers only)

#### Step-by-Step Setup
1. **Go to Profiles** → Select your resin profile
2. **Find Ring Exposure Enabled** → Set to **1**
3. **Set Ring Thickness** → Start with **0.5 mm**
4. **Set Ring Exposure Reduction** → Start with **50%**
5. **Set Ring Exposure Mode** → Use **0** (burn-in layers only)
6. **Test with a small print** to verify effectiveness

#### Fine-tuning Ring Exposure
- **Too much reduction**: Parts may not stick properly
- **Too little reduction**: Elephant foot may still occur
- **Thick rings**: May affect fine details
- **Thin rings**: May not provide enough protection

### EFME (Elephant Foot Mitigation Enhanced)

#### What It Does
EFME provides advanced elephant foot mitigation with multiple application modes and continuous operation options for maximum effectiveness.

#### When to Use EFME
- **Severe elephant foot** that Ring Exposure can't fix
- **High-precision parts** requiring perfect dimensions
- **Production printing** where consistency is critical
- **Complex geometries** with challenging base layers

#### Configuration Options
1. **EFME Mode**: Choose application mode
   - **Mode 0**: Burn-in layers only (recommended)
   - **Mode 1**: All layers (maximum quality)
   - **Mode 2**: Selected layers (custom control)

2. **EFME Parameters**:
   - **EFME Max Layer**: Maximum layer for application
   - **EFME Continuous**: Enable continuous timing
   - **EFME Guard Band**: Protective exposure zones

#### Step-by-Step EFME Setup
1. **Go to Profiles** → Select your resin profile
2. **Find EFME Mode** → Set to **0** (burn-in layers)
3. **Set EFME Max Layer** → Use **5** (5 base layers)
4. **Enable EFME Continuous** → Set to **1**
5. **Set EFME Guard Band** → Use **0.3 mm**
6. **Test thoroughly** before production use

## Advanced Techniques

### Multi-Stage Base Layer Exposure

#### What It Does
Multi-stage exposure uses different exposure patterns for the base layers, creating a more controlled curing process that reduces elephant foot.

#### Configuration
1. **Base Layer Seed Size**: Start with **0.5 mm**
2. **Base Layer Seed Spacing**: Use **1.0 mm**
3. **Base Layer Seed Exposure**: Use **5 seconds**
4. **Base Layer Lattice Exposure**: Use **8 seconds**
5. **Base Layer Final Exposure**: Use **12 seconds**

#### When to Use
- **High-precision parts** requiring perfect base layers
- **Complex geometries** with challenging adhesion
- **Production environments** where consistency is critical
- **Research applications** requiring precise dimensions

### Adaptive Base Layer Thickness

#### What It Does
Automatically adjusts base layer thickness based on model geometry, providing optimal adhesion without over-exposure.

#### Configuration
1. **Enable Adaptive Slicing**: Set to **1**
2. **Set Min Layer Height**: Use **0.025 mm**
3. **Set Max Layer Height**: Use **0.075 mm**
4. **Base Layer Count**: Use **3-5 layers**

#### Benefits
- **Automatic optimization** based on model complexity
- **Consistent quality** across different models
- **Reduced manual tuning** required
- **Better material efficiency**

## Troubleshooting Elephant Foot

### Problem: Still Getting Elephant Foot

#### Check These Settings
1. **Base layer cure time** is too high
2. **Ring exposure** is not properly configured
3. **Build platform** is not properly leveled
4. **Z-zero** is set incorrectly
5. **Resin temperature** is too high

#### Solutions to Try
1. **Reduce base layer cure time** by 2-3 seconds
2. **Increase ring exposure reduction** to 60-70%
3. **Re-level build platform** with proper calibration
4. **Check Z-zero** with a feeler gauge
5. **Lower room temperature** or use a fan

### Problem: Parts Not Sticking

#### Check These Settings
1. **Ring exposure reduction** is too aggressive
2. **Base layer cure time** is too low
3. **Build platform** is not properly prepared
4. **Resin temperature** is too low

#### Solutions to Try
1. **Reduce ring exposure reduction** to 30-40%
2. **Increase base layer cure time** by 2-3 seconds
3. **Re-prepare build platform** surface
4. **Increase room temperature** or use a heater

### Problem: Inconsistent Results

#### Check These Settings
1. **Temperature fluctuations** during printing
2. **Resin age and contamination**
3. **Build platform wear** and tear
4. **Profile settings** not saved properly

#### Solutions to Try
1. **Stabilize room temperature** with climate control
2. **Use fresh, uncontaminated resin**
3. **Replace or refurbish build platform**
4. **Verify profile settings** are properly saved

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
- **Perfect base layers** are worth the extra time
- **Consistent quality** is more important than fast printing
- **Invest in good tools** for measurement and calibration

## Real-World Examples

### Example 1: Standard Resin Profile
```
Base Layer Cure Time: 15 seconds
Base Layer Count: 4 layers
Ring Exposure: Enabled (0.5mm, 50% reduction)
EFME: Disabled (not needed for standard use)
Result: Clean base layers, no elephant foot
```

### Example 2: High-Precision Profile
```
Base Layer Cure Time: 12 seconds
Base Layer Count: 5 layers
Ring Exposure: Enabled (0.3mm, 60% reduction)
EFME: Enabled (Mode 0, 5 layers)
Result: Perfect dimensional accuracy
```

### Example 3: Fast Production Profile
```
Base Layer Cure Time: 18 seconds
Base Layer Count: 3 layers
Ring Exposure: Enabled (0.7mm, 40% reduction)
EFME: Disabled (for speed)
Result: Good quality with faster printing
```


<img src="data:image/png;base64,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" alt="Middle exposure">
<br>
<br>

But when ```Middle Exposure``` enabled, only middle section cured for 50s and outside area for 10s.

<img src="data:image/png;base64,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" alt="Middle exposure / double exposure">

## Next Steps

Once you've mastered elephant foot mitigation:
- **[Profile Management]({{<ref "profiles">}})** - Create optimized profiles for different materials
- **[Advanced Slicing]({{<ref "advanced-slicing">}})** - Fine-tune slicing for optimal results
- **[Print Quality]({{<ref "print-quality">}})** - Monitor and improve overall quality
- **[Machine Configuration]({{<ref "machine-configuration">}})** - Optimize hardware settings

## Related Topics

- [Profile Management]({{<ref "profiles">}}) - Configure resin-specific settings
- [Advanced Slicing]({{<ref "advanced-slicing">}}) - Fine-tune slicing parameters
- [Print Quality]({{<ref "print-quality">}}) - Monitor and improve results
- [Machine Configuration]({{<ref "machine-configuration">}}) - Hardware setup and calibration

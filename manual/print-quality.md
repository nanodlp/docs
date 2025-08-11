---
title: "Print Quality Optimization"
description: "Complete guide to achieving optimal print quality in NanoDLP through proper configuration, monitoring, and troubleshooting."
lead: "Learn how to diagnose, fix, and prevent common print quality issues to achieve professional results every time."
draft: false
menu:
  docs:
    parent: "manual"
images: []
toc: true
---

## Understanding Print Quality

Print quality in resin 3D printing refers to how accurately your printed object matches the intended design. High-quality prints have:
- **Smooth surfaces** without visible layer lines
- **Accurate dimensions** that match the original model
- **Strong layer adhesion** without delamination
- **Clean details** with sharp edges and features
- **Consistent results** across multiple prints

### Why Quality Matters
- **Professional appearance** for display or commercial use
- **Functional accuracy** for parts that need to fit together
- **Time savings** from fewer failed prints
- **Material efficiency** from optimized settings
- **Customer satisfaction** for commercial applications

## Common Quality Issues and Solutions

### 1. Layer Lines and Surface Roughness

#### What You'll See
- Visible horizontal lines across surfaces
- Rough, textured surfaces instead of smooth ones
- Uneven layer heights
- "Stair-stepping" on curved surfaces

#### Root Causes
- **Layer height too thick** for the detail level needed
- **Insufficient anti-aliasing** settings
- **Poor layer adhesion** causing uneven surfaces
- **Incorrect exposure times** for the resin

#### Solutions

##### Step 1: Optimize Layer Height
1. **Go to Profiles** → Select your resin profile
2. **Set Layer Height** based on your needs:
   - **High detail**: 0.025-0.05 mm
   - **Standard quality**: 0.05-0.075 mm
   - **Fast printing**: 0.075-0.1 mm
3. **Test with a small model** to verify quality improvement

##### Step 2: Enable Anti-Aliasing
1. **Find Anti-Alias 3D** → Set to **1** (enabled)
2. **Set Anti-Alias Threshold** to **0.5** (start with default)
3. **Print a test model** with curved surfaces
4. **Adjust threshold** if needed (lower = smoother but slower)

##### Step 3: Optimize Exposure Settings
1. **Check cure time** for your resin type
2. **Verify resin temperature** (20-25°C recommended)
3. **Test different exposure times** with calibration models
4. **Document successful settings** for future reference

### 2. Poor Layer Adhesion

#### What You'll See
- Layers separating during printing
- Weak, brittle prints that break easily
- Gaps between layers
- Print failures partway through

#### Root Causes
- **Insufficient cure time** for the resin
- **Poor resin quality** or contamination
- **Incorrect temperature** affecting resin properties
- **Inadequate support structures**

#### Solutions

##### Step 1: Optimize Cure Time
1. **Start with manufacturer recommendations** for your resin
2. **Test with calibration models** to find the sweet spot
3. **Increase cure time** by 1-2 seconds if layers don't stick
4. **Monitor resin temperature** during printing

##### Step 2: Enable Multi-Cure
1. **Find Multi Cure Gap** → Set to **0.1 mm**
2. **Set Cure Passes** to **2** (start with 2 passes)
3. **Test with a small model** to verify improvement
4. **Increase passes** to 3-4 for difficult materials if needed

##### Step 3: Check Support Configuration
1. **Verify support density** is adequate
2. **Check support thickness** for strength
3. **Ensure proper support placement** on overhangs
4. **Test support removal** after printing

### 3. Dimensional Inaccuracy

#### What You'll See
- Parts don't fit together properly
- Measurements don't match the model
- Inconsistent sizing across different prints
- Assembly problems with multi-part models

#### Root Causes
- **Incorrect resolution settings** for your printer
- **Poor calibration** of the build platform
- **Resin shrinkage** not properly compensated
- **Temperature fluctuations** during printing

#### Solutions

##### Step 1: Calibrate Display Resolution
1. **Go to Display Calibration** in settings
2. **Use boundary calibration** to verify full display coverage
3. **Check resolution settings** match your hardware
4. **Test with known dimensions** (calibration cube)

##### Step 2: Compensate for Resin Shrinkage
1. **Measure printed parts** with calipers
2. **Calculate shrinkage percentage** compared to model
3. **Adjust scaling** in your slicing software
4. **Test and refine** until dimensions are correct

##### Step 3: Stabilize Environment
1. **Maintain consistent temperature** (20-25°C)
2. **Avoid drafts and air currents** near your printer
3. **Use consistent resin** from the same batch
4. **Monitor humidity** and keep it stable

### 4. Surface Defects and Artifacts

#### What You'll See
- Pockmarks or holes in surfaces
- Rough patches or inconsistent finish
- Support marks that don't clean up
- Uneven surface quality across the model

#### Root Causes
- **Insufficient support density** in problem areas
- **Poor resin quality** or contamination
- **Incorrect exposure settings** for the material
- **Build platform issues** affecting adhesion

#### Solutions

##### Step 1: Optimize Support Settings
1. **Increase support density** in problem areas
2. **Adjust support thickness** for better strength
3. **Use different support types** for different areas
4. **Test support removal** to find optimal settings

##### Step 2: Check Resin Quality
1. **Use fresh, uncontaminated resin**
2. **Filter resin** if it contains particles
3. **Store resin properly** to avoid degradation
4. **Check expiration dates** on resin bottles

##### Step 3: Fine-tune Exposure
1. **Test different cure times** with small models
2. **Verify exposure consistency** across layers
3. **Check for over-curing** which can cause surface issues
4. **Document successful settings** for each material

## Quality Optimization Workflow

### Step 1: Baseline Assessment
1. **Print a calibration model** (20x20x20mm cube)
2. **Measure all dimensions** with calipers
3. **Photograph surfaces** for visual assessment
4. **Document current settings** and results

### Step 2: Systematic Testing
1. **Change one variable at a time** to isolate issues
2. **Test with consistent models** for comparison
3. **Measure and document** all results
4. **Identify the most impactful** improvements

### Step 3: Profile Optimization
1. **Create optimized profiles** for different quality levels
2. **Test profiles thoroughly** before production use
3. **Document successful configurations** for team use
4. **Regular profile updates** based on new learnings

### Step 4: Continuous Monitoring
1. **Monitor print quality** on every print
2. **Track quality metrics** over time
3. **Identify trends** and potential issues
4. **Proactively adjust** settings before problems occur

## Advanced Quality Techniques

### Adaptive Slicing for Quality

#### What It Does
Automatically adjusts layer thickness based on model geometry, providing optimal quality where needed while maintaining efficiency.

#### Configuration
1. **Enable Adapt Slicing**: Set to **1**
2. **Set Min Layer Height**: Use **0.025 mm**
3. **Set Max Layer Height**: Use **0.1 mm**
4. **Test with complex models** to verify effectiveness

#### Benefits
- **Better detail** in complex areas
- **Faster printing** in simple areas
- **Consistent quality** across the entire model
- **Automatic optimization** based on geometry

### Multi-Cure for Enhanced Quality

#### What It Does
Performs multiple curing passes per layer, improving adhesion and surface quality.

#### Configuration
1. **Set Multi Cure Gap**: Use **0.1 mm**
2. **Set Cure Passes**: Start with **2**, increase if needed
3. **Monitor print time** impact
4. **Test quality improvement** with challenging models

#### When to Use
- **High-quality requirements** for professional use
- **Difficult materials** that need extra curing
- **Complex geometries** with challenging features
- **Production quality** standards

### Anti-Aliasing for Smooth Surfaces

#### What It Does
Smooths edges and reduces stair-stepping for professional-quality surfaces.

#### Configuration
1. **Enable Anti-Alias 3D**: Set to **1**
2. **Set Threshold**: Start with **0.5**, adjust as needed
3. **Test with curved surfaces** to verify improvement
4. **Balance quality vs. speed** for your needs

#### Best Applications
- **Curved surfaces** and organic shapes
- **Display models** where appearance matters
- **Professional applications** requiring smooth finish
- **High-detail models** with fine features

## Quality Monitoring and Maintenance

### Regular Quality Checks

#### Daily Monitoring
1. **Check first layers** of every print
2. **Monitor print progress** for obvious issues
3. **Verify resin level** and quality
4. **Clean build platform** between prints

#### Weekly Assessment
1. **Print calibration models** to verify settings
2. **Check surface quality** of recent prints
3. **Measure dimensional accuracy** with known models
4. **Review and update** quality settings

#### Monthly Maintenance
1. **Deep clean** build platform and FEP
2. **Calibrate display** and check resolution
3. **Update profiles** based on learnings
4. **Review quality metrics** and trends

### Quality Metrics to Track

#### Dimensional Accuracy
- **X, Y, Z measurements** vs. model dimensions
- **Consistency** across multiple prints
- **Assembly fit** for multi-part models
- **Tolerance compliance** for functional parts

#### Surface Quality
- **Surface roughness** measurements
- **Layer line visibility** assessment
- **Support mark cleanup** effectiveness
- **Overall finish** appearance

#### Print Reliability
- **Success rate** percentage
- **Failure types** and frequency
- **Print time** consistency
- **Material usage** efficiency

## Troubleshooting Quality Issues

### Problem: Inconsistent Quality

#### Check These Areas
1. **Temperature stability** during printing
2. **Resin consistency** and age
3. **Profile settings** are properly saved
4. **Hardware calibration** is current

#### Solutions
1. **Stabilize environment** with climate control
2. **Use consistent resin** from same batch
3. **Verify profile settings** are saved correctly
4. **Re-calibrate hardware** if needed

### Problem: Quality Degradation Over Time

#### Check These Areas
1. **FEP film condition** and wear
2. **Build platform surface** preparation
3. **Resin contamination** or degradation
4. **Hardware wear** and tear

#### Solutions
1. **Replace FEP film** if worn or damaged
2. **Re-prepare build platform** surface
3. **Use fresh, clean resin**
4. **Maintain hardware** according to schedule

### Problem: Specific Areas Have Poor Quality

#### Check These Areas
1. **Support configuration** in problem areas
2. **Model orientation** and overhangs
3. **Layer height consistency** across the model
4. **Exposure settings** for different areas

#### Solutions
1. **Increase support density** in problem areas
2. **Adjust model orientation** to minimize overhangs
3. **Use adaptive slicing** for consistent quality
4. **Fine-tune exposure** for challenging areas

## Best Practices for Quality

### 1. Start with Quality
- **Don't sacrifice quality** for speed initially
- **Perfect your settings** before optimizing for speed
- **Quality is more important** than fast printing
- **Good quality saves time** in the long run

### 2. Systematic Approach
- **Test one variable at a time** to isolate issues
- **Document everything** including failures
- **Learn from each print** to improve the next
- **Don't make multiple changes** simultaneously

### 3. Consistent Environment
- **Maintain stable temperature** throughout printing
- **Use consistent materials** and supplies
- **Regular maintenance** prevents quality issues
- **Monitor conditions** during printing

### 4. Continuous Improvement
- **Track quality metrics** over time
- **Identify trends** and potential issues
- **Update procedures** based on learnings
- **Share knowledge** with your team

## Next Steps

Once you've optimized print quality:
- **[Profile Management]({{<ref "profiles">}})** - Create optimized profiles for different materials
- **[Advanced Slicing]({{<ref "advanced-slicing">}})** - Fine-tune slicing for optimal results
- **[Elephant Foot Mitigation]({{<ref "elephant-foot">}})** - Perfect base layer quality
- **[Machine Configuration]({{<ref "machine-configuration">}})** - Optimize hardware settings

## Related Topics

- [Profile Management]({{<ref "profiles">}}) - Configure resin-specific settings
- [Advanced Slicing]({{<ref "advanced-slicing">}}) - Fine-tune slicing parameters
- [Elephant Foot Mitigation]({{<ref "elephant-foot">}}) - Perfect base layers
- [Machine Configuration]({{<ref "machine-configuration">}}) - Hardware setup and calibration

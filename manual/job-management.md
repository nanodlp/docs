---
title: "Job Management"
description: "Complete guide to managing 3D printing jobs, workflows, and print operations in NanoDLP."
lead: "Learn how to create, manage, and control 3D printing jobs for optimal results."
draft: false
menu:
  docs:
    parent: "manual"
images: []
toc: true
---

## Overview

Job management in NanoDLP encompasses all aspects of creating, organizing, and controlling 3D printing jobs. This guide focuses on practical workflows and common tasks rather than just listing features. Whether you're printing your first model or managing a production workflow, these step-by-step instructions will help you succeed.

## Your First Print: Complete Workflow

### Step 1: Prepare Your 3D Model
1. **File Requirements**:
   - **Supported formats**: STL, 3MF, OBJ, SLC, NSLICE, SVG
   - **File size**: Keep under 100MB for best performance
   - **Model orientation**: Ensure proper orientation for printing
   - **Supports**: Add supports if needed (many slicers can do this)

2. **Model Preparation**:
   - **Check for errors**: Use a 3D modeling tool to verify mesh integrity
   - **Optimize size**: Scale to your desired dimensions
   - **Consider supports**: Plan where supports will be needed

### Step 2: Upload and Create Job
1. **Access the Plates Page**:
   - Go to **Plates** in the main menu
   - Click **Add Plate** to create a new job

2. **Upload Your Model**:
   - Drag and drop your file or click to browse
   - Wait for upload to complete
   - Verify the model appears correctly

3. **Configure Basic Settings**:
   - **Select Profile**: Choose the appropriate resin profile
   - **Layer Height**: Set your desired resolution (0.025-0.1 mm)
   - **Supports**: Enable if your model needs them

### Step 3: Slice and Prepare
1. **Start Slicing**:
   - Click **Slice** to begin processing
   - Monitor progress in the job status
   - Wait for completion (time varies with model complexity)

2. **Review Results**:
   - Check layer count and estimated print time
   - Preview layers to ensure quality
   - Verify support placement if applicable

### Step 4: Start Printing
1. **Pre-Print Checklist**:
   - Resin level is adequate
   - Build platform is clean and level
   - FEP film is in good condition
   - Printer is properly calibrated

2. **Begin Print**:
   - Click **Print** to start
   - Monitor first few layers carefully
   - Check for proper adhesion and layer formation

## Daily Job Management

### Managing Multiple Jobs

#### Job Organization
- **Active Jobs**: Currently printing or queued
- **Completed Jobs**: Successfully finished prints
- **Failed Jobs**: Jobs that encountered errors
- **Archived Jobs**: Long-term storage

#### Job Status Tracking
- **Pending**: Waiting to be processed
- **Slicing**: Currently being sliced
- **Queued**: Ready for printing
- **Printing**: Currently being printed
- **Paused**: Temporarily stopped
- **Completed**: Successfully finished
- **Failed**: Encountered errors

### Common Daily Tasks

#### Starting a New Print
1. **Check Printer Status**: Ensure printer is ready
2. **Upload Model**: Add new 3D model
3. **Select Profile**: Choose appropriate resin profile
4. **Slice Model**: Process for printing
5. **Start Print**: Begin printing operation

#### Monitoring Active Prints
1. **Check Progress**: Monitor layer completion
2. **Verify Quality**: Look for layer adhesion issues
3. **Track Time**: Monitor elapsed and remaining time
4. **Handle Issues**: Pause or stop if problems arise

#### Managing Completed Jobs
1. **Review Results**: Check print quality
2. **Document Settings**: Note successful configurations
3. **Clean Up**: Remove completed jobs or archive them
4. **Plan Next**: Prepare for upcoming prints

## Advanced Job Features

### Job Cloning and Templates

#### When to Use Cloning
- **Similar Models**: Multiple versions of the same design
- **Batch Production**: Multiple copies of the same model
- **Parameter Testing**: Try different settings on the same model
- **Team Workflows**: Share successful configurations

#### How to Clone Jobs
1. **Select Source Job**: Choose the job to clone
2. **Click Clone**: Use the clone function
3. **Modify Settings**: Adjust parameters as needed
4. **Save New Job**: Create the cloned version

#### Creating Templates
1. **Start with Success**: Use a working job as a base
2. **Remove Specifics**: Clear model-specific settings
3. **Add Documentation**: Include usage notes
4. **Test Thoroughly**: Verify template works correctly

### Batch Operations

#### Managing Multiple Jobs
1. **Queue Management**: Organize print order
2. **Priority Setting**: Set job priorities
3. **Resource Planning**: Plan resin and time requirements
4. **Quality Control**: Monitor multiple prints simultaneously

#### Production Workflows
1. **Standardized Setup**: Use consistent profiles and settings
2. **Quality Checks**: Regular quality verification
3. **Efficiency Optimization**: Minimize setup time between jobs
4. **Documentation**: Track successful configurations

## Troubleshooting Common Issues

### Print Failures

#### Layer Adhesion Problems
**Symptoms**: Layers separating, weak prints
**Solutions**:
- Check resin profile settings (cure time, lift speed)
- Verify resin temperature and viscosity
- Ensure proper support configuration
- Check layer height settings

#### Support Issues
**Symptoms**: Weak supports, difficult removal
**Solutions**:
- Increase support cure time
- Check support density and thickness
- Verify support placement and orientation
- Consider different support strategies

#### Print Stuck to FEP
**Symptoms**: Print adheres to FEP instead of build platform
**Solutions**:
- Check build platform leveling
- Verify first layer exposure settings
- Ensure proper support configuration
- Check resin viscosity and temperature

### System Issues

#### Slicing Problems
**Symptoms**: Slicing fails or produces errors
**Solutions**:
- Check file format and integrity
- Verify model mesh quality
- Reduce file size if too large
- Check system resources

#### Job Management Issues
**Symptoms**: Jobs disappear or can't be managed
**Solutions**:
- Check file permissions
- Verify storage space
- Restart the system if needed
- Check for corrupted job files

## Best Practices for Success

### Job Preparation
1. **Plan Ahead**: Organize jobs and materials in advance
2. **Test First**: Use small models to test new configurations
3. **Document Everything**: Keep notes on successful settings
4. **Quality First**: Don't sacrifice quality for speed

### Workflow Optimization
1. **Standardize Processes**: Use consistent workflows
2. **Batch Similar Jobs**: Group similar prints together
3. **Monitor Resources**: Track resin usage and time
4. **Regular Maintenance**: Keep system clean and calibrated

### Quality Control
1. **Check First Layers**: Monitor initial layer formation
2. **Regular Inspection**: Check prints during operation
3. **Post-Print Review**: Evaluate final quality
4. **Continuous Improvement**: Learn from each print

## File Management

### Supported Formats
- **STL**: Most common, widely supported
- **3MF**: Modern format with better metadata
- **OBJ**: Good for complex geometries
- **SLC**: Sliced format for direct printing
- **NSLICE**: NanoDLP-specific format
- **SVG**: 2D vector format for special applications

### File Organization
1. **Clear Naming**: Use descriptive file names
2. **Folder Structure**: Organize by project or type
3. **Version Control**: Keep track of file versions
4. **Backup Strategy**: Maintain file backups

## USB and External Storage

### Using USB Storage
1. **Mount USB Device**: Insert and mount USB drive
2. **Access Files**: Browse USB contents in NanoDLP
3. **Copy to Local**: Transfer files to local storage
4. **Manage Storage**: Organize and clean up files

### Best Practices
- **Format USB**: Use FAT32 for best compatibility
- **File Organization**: Keep files organized on USB
- **Regular Backup**: Don't rely solely on USB storage
- **Virus Protection**: Scan USB devices before use

## Next Steps

Once you're comfortable with job management:
- **[Profile Management]({{<ref "profiles">}})** - Optimize resin settings for better results
- **[Advanced Slicing]({{<ref "advanced-slicing">}})** - Fine-tune slicing for optimal quality
- **[Print Quality]({{<ref "print-quality">}})** - Monitor and improve print results
- **[Hardware Management]({{<ref "hardware-management">}})** - Maintain and optimize your printer

## Related Topics

- [Profile Management]({{<ref "profiles">}}) - Configure resin-specific settings
- [Advanced Slicing]({{<ref "advanced-slicing">}}) - Fine-tune slicing parameters
- [Print Quality]({{<ref "print-quality">}}) - Monitor and improve results
- [Hardware Management]({{<ref "hardware-management">}}) - Maintain your printer

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

Job management in NanoDLP encompasses all aspects of creating, organizing, and controlling 3D printing jobs. This includes job creation, print control, workflow management, and monitoring for efficient 3D printing operations.

## Job Creation and Setup

### Job Creation Methods
- **File Upload**: Upload 3D models to create jobs
- **USB File Access**: Direct access to files on mounted USB devices
- **Job Cloning**: Clone existing jobs with modifications
- **Job Import**: Import jobs from external sources
- **Template Jobs**: Use predefined job templates

### Supported File Formats
- **3D Models**: STL, 3MF, OBJ, SLC, NSLICE, SVG
- **Sliced Files**: NanoDLP, CWS
- **Archives**: ZIP files containing PNG layers
- **Size Limits**: Configurable file size restrictions

### Job Configuration
- **Profile Selection**: Choose appropriate print profiles
- **Parameter Settings**: Configure print parameters
- **Support Generation**: Set up support structures
- **Quality Settings**: Define quality requirements

### Job Validation
- **File Integrity**: Verify uploaded files
- **Parameter Validation**: Check parameter compatibility
- **Resource Requirements**: Assess resource needs
- **Pre-print Checks**: Validate job before printing

## Print Control Operations

### Basic Print Control
- **Start Printing**: Begin print operations
- **Stop Printing**: Halt print operations
- **Pause Printing**: Temporarily pause prints
- **Resume Printing**: Continue paused prints

### Advanced Print Control
- **Force Stop**: Emergency stop operations
- **Print After Slice**: Start printing after slicing completion
- **Resume from Specific Point**: Resume from specific layers
- **Print Queue Management**: Manage multiple print jobs

### Print Monitoring
- **Real-time Status**: Monitor print progress
- **Layer Tracking**: Track current layer progress
- **Time Monitoring**: Monitor elapsed and remaining time
- **Quality Monitoring**: Monitor print quality during operation

## Job Organization and Management

### Job Categories
- **Active Jobs**: Currently queued or printing jobs
- **Completed Jobs**: Successfully finished prints
- **Failed Jobs**: Jobs that encountered errors
- **Archived Jobs**: Long-term storage jobs
- **Deleted Jobs**: Jobs marked for deletion

### Job Status Tracking
- **Pending**: Waiting to be processed
- **Slicing**: Currently being sliced
- **Queued**: Ready for printing
- **Printing**: Currently being printed
- **Paused**: Temporarily stopped
- **Completed**: Successfully finished
- **Failed**: Encountered errors

### Job History
- **Print Records**: Complete print history
- **Performance Metrics**: Print time and quality data
- **Error Logs**: Detailed error information
- **Success Rates**: Track successful vs. failed prints

## Advanced Job Features

### Job Cloning and Duplication
- **Exact Cloning**: Create identical copies
- **Modified Cloning**: Clone with parameter changes
- **Batch Cloning**: Create multiple similar jobs
- **Template Management**: Use jobs as templates

### Job Restoration
- **Deleted Job Recovery**: Restore accidentally deleted jobs
- **Backup Restoration**: Restore from backup files


### Job Repair and Maintenance
- **File Repair**: Fix corrupted job files
- **Parameter Correction**: Fix incorrect parameters
- **Support Regeneration**: Regenerate support structures
- **Quality Optimization**: Optimize job settings

## Export and Compatibility

### Supported Export Formats
NanoDLP supports export to 20+ industry-standard formats:

#### **Resin 3D Printing Formats**
- **NanoDLP (.nanodlp)**: Native format with full feature support
- **CBDDLP (.cbddlp)**: Chitubox format compatibility
- **Photon (.photon)**: Anycubic Photon format
- **CTB (.ctb)**: Chitubox binary format
- **CWS (.cws)**: Chitubox workspace format

#### **Professional Formats**
- **SL1 (.sl1)**: Prusa SL1 format
- **UVJ (.uvj)**: UVTools format
- **ZCODEX (.zcodex)**: Zortrax format
- **PWS (.pws)**: Prusa workspace format
- **PW0 (.pw0)**: Prusa format variant

#### **Archive and Compression**
- **CZIP (.czip)**: Compressed archive format
- **ZIP (.zip)**: Standard archive with PNG layers

#### **Specialized Formats**
- **FDG (.fdg)**: Formlabs format
- **LGS (.lgs, .lgs30)**: Layer format variants
- **PHZ (.phz)**: Specialized format support

### Export Features
- **Quality Preservation**: Maintain slicing quality across formats
- **Batch Export**: Export to multiple formats simultaneously
- **Format Validation**: Ensure compatibility with target printers
- **Metadata Preservation**: Maintain job settings and parameters

## Advanced Job Configuration

### Auto-Centering Options
- **Center Pieces**: Automatically center all objects on the build platform
- **Center Origin**: Center based on model origin point
- **Disable**: No automatic centering applied

### Adaptive Layer Thickness
- **Multiple Thickness**: Configure different layer heights at specific Z positions
- **Format**: `height:thickness,mm:micron` (e.g., "10:0.05,20:0.1")
- **Dynamic Adjustment**: Automatic layer height optimization based on geometry

### Multi-Cure Settings
- **Multiple Cure Times**: Set different exposure times for the same layer
- **Format**: Comma-separated values in seconds
- **Applications**: Complex geometries, difficult materials, quality enhancement

### Advanced Positioning
- **Offset Control**: Adjust lowest point for slicing (in mm)
- **Stop Layers**: Define specific layers to pause printing
- **Low Quality Layers**: Configure reduced quality for specific layer ranges

### Custom Masking
- **Job-Specific Masks**: Override global mask files per job
- **Mask Intensity Control**: Adjust mask effect percentage (0-100%)
- **Format Support**: PNG mask files for custom exposure patterns

### Layer Manipulation
- **Image Rotation**: Rotate layers 90° or maintain profile settings
- **Custom Orientation**: Override profile rotation settings
- **Layer-Specific Adjustments**: Fine-tune individual layer properties

## Workflow Management

### Print Workflows
- **Standard Workflow**: Basic print process
- **Advanced Workflow**: Complex multi-step processes
- **Batch Workflow**: Multiple job processing
- **Custom Workflow**: User-defined workflows

### Quality Control
- **Pre-Print Checks**: Validate settings before printing
- **In-Process Monitoring**: Monitor print quality
- **Post-Print Inspection**: Quality assessment
- **Quality Metrics**: Track quality over time

### Optimization
- **Parameter Tuning**: Optimize print parameters
- **Material Optimization**: Optimize for specific materials
- **Speed Optimization**: Balance quality and speed
- **Support Optimization**: Optimize support structures

## Job Analytics and Monitoring

### Performance Metrics
- **Print Time**: Track printing duration
- **Material Usage**: Monitor material consumption
- **Success Rate**: Track successful prints
- **Quality Scores**: Assess print quality

### Cost Analysis
- **Material Costs**: Calculate material expenses
- **Time Costs**: Factor in printing time
- **Energy Costs**: Monitor power consumption
- **Total Cost**: Complete cost analysis

### Trend Analysis
- **Performance Trends**: Track improvements over time
- **Quality Trends**: Monitor quality changes
- **Efficiency Trends**: Track efficiency improvements
- **Cost Trends**: Monitor cost changes

## Advanced Features

### Multi-Job Printing
- **Batch Processing**: Process multiple jobs simultaneously
- **Queue Management**: Manage print queues
- **Priority Setting**: Set print priorities
- **Resource Allocation**: Allocate resources efficiently

### Remote Management
- **Remote Job Creation**: Create jobs remotely
- **Remote Monitoring**: Monitor prints remotely
- **Remote Control**: Control prints remotely
- **Mobile Access**: Access via mobile devices

### Integration
- **External Slicers**: Integrate with external slicing software
- **Cloud Services**: Connect to cloud storage
- **Design Software**: Integrate with CAD software
- **Workflow Systems**: Connect to external workflow systems

## Job Control API

### REST API Endpoints
- **Job Creation**: Create new jobs via API
- **Job Control**: Control job operations via API
- **Job Status**: Get job status information
- **Job Management**: Manage job lifecycle via API

### Automation
- **Scripted Job Creation**: Automate job creation
- **Batch Job Processing**: Process multiple jobs automatically
- **Scheduled Jobs**: Schedule jobs for specific times
- **Conditional Job Execution**: Execute jobs based on conditions

## Best Practices

### Job Preparation
- **Model Optimization**: Optimize 3D models before job creation
- **Parameter Validation**: Validate all parameters
- **Support Verification**: Verify support structures
- **Quality Pre-check**: Check quality settings before printing

### Organization
- **Naming Conventions**: Use consistent job naming
- **Folder Structure**: Organize jobs logically
- **Version Control**: Track job versions
- **Backup Strategy**: Implement backup procedures

### Quality Assurance
- **Pre-Print Testing**: Test settings before full prints
- **Parameter Validation**: Validate all parameters
- **Support Verification**: Verify support structures
- **Quality Monitoring**: Monitor print quality continuously

## Troubleshooting

### Common Issues
- **Job Creation Failures**: Resolve job creation problems
- **Print Failures**: Fix print problems
- **Quality Issues**: Address quality problems
- **Workflow Errors**: Resolve workflow issues

### Error Resolution
- **Error Analysis**: Analyze error messages
- **Problem Identification**: Identify root causes
- **Solution Implementation**: Apply solutions
- **Prevention Measures**: Prevent future issues

## Related Topics

- **[Job Control]({{<ref "job">}})** - Basic job control operations
- **[Web Interface]({{<ref "web-interface">}})** - Web interface usage
- **[API Reference]({{<ref "api-reference">}})** - Programmatic access
- **[Print Quality]({{<ref "print-quality">}})** - Quality optimization
- **[Calibration Jobs]({{<ref "calibration-job">}})** - Calibration procedures
- **[Plate Management]({{<ref "plate-management">}})** - File and plate operations

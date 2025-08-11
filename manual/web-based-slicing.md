---
title: "Web-Based Slicing (WASM)"
description: "Complete guide to browser-based slicing using WebAssembly technology in NanoDLP."
lead: "Learn how to use client-side slicing for improved performance and real-time processing."
draft: false
menu:
  docs:
    parent: "manual"
images: []
toc: true
---

# Web-Based Slicing (WASM)

## Overview
NanoDLP's web-based slicing feature utilizes WebAssembly (WASM) technology to perform slicing operations directly in the user's browser. This provides significant performance improvements, especially on ARM-based devices, and enables real-time slicing with immediate feedback.

## Benefits of Web-Based Slicing

### Performance Improvements
- **Client-Side Processing**: Offloads processing from the server to the client
- **Reduced Server Load**: Server resources are freed for other operations
- **Parallel Processing**: Multiple users can slice simultaneously
- **Real-Time Feedback**: Immediate progress updates during slicing

### Platform Optimization
- **ARM Device Support**: Optimized performance for Raspberry Pi and similar devices
- **Browser Optimization**: Leverages modern browser capabilities
- **Memory Efficiency**: Better memory management for large files
- **Network Independence**: Reduced dependency on network performance

## How It Works

### WebAssembly Technology
- **Compiled Code**: High-performance compiled code running in the browser
- **Cross-Platform**: Works on any device with a modern web browser
- **Native Speed**: Near-native performance for complex operations
- **Memory Safety**: Secure execution environment

### Slicing Process
1. **File Upload**: 3D model files are uploaded to the browser
2. **WASM Initialization**: WebAssembly modules are loaded and initialized
3. **Geometry Processing**: Model geometry is analyzed and processed
4. **Layer Generation**: Individual layers are generated with full resolution
5. **Progress Tracking**: Real-time progress updates are displayed
6. **Result Export**: Sliced data is exported in various formats

## Supported File Formats

### Input Formats
- **STL Files**: Standard stereolithography format
- **3MF Files**: 3D Manufacturing Format
- **OBJ Files**: Wavefront Object format
- **SLC Files**: Slice format
- **SVG Files**: Scalable Vector Graphics


This web-based slicing system provides users with powerful, client-side processing capabilities while maintaining the high quality and feature-rich experience that NanoDLP is known for.


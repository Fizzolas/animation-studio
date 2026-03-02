# Core Engine

This directory contains the performance-critical native core components of the Animation Studio.

## Structure

- `engine/` - Core rendering and animation engine (C++)
- `scene/` - Scene graph, node system, and data structures
- `render/` - Rendering pipeline for 2D and 3D content
- `animation/` - Animation system (keyframes, curves, timelines)
- `physics/` - Physics simulation and deformation systems
- `io/` - File import/export handlers for all supported formats
- `bindings/` - Python bindings via pybind11

## Technology

- **Language**: C++ (C++17 or later)
- **Rendering**: To be determined (Vulkan/OpenGL/DirectX)
- **Python Bindings**: pybind11
- **Math Library**: GLM or similar

## Building

Build instructions will be added as the core is developed.

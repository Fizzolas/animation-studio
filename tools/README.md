# Built-in Tools

This directory contains the default tool plugins that ship with Animation Studio.

## Structure

- `drawing/` - 2D drawing and painting tools
- `modeling/` - 3D modeling and sculpting tools
- `animation/` - Animation and rigging tools
- `effects/` - Visual effects and modifiers
- `camera/` - Camera controls and manipulation
- `selection/` - Selection and transformation tools
- `rendering/` - Rendering and output tools

## Tool Plugin System

Each tool is a self-contained plugin that can be:
- Hot-swapped without restarting
- Modified or replaced by users
- Extended through the scripting API
- Shared via the workshop

## Creating Tools

Tools can be written in:
- **Python**: For rapid development and scripting
- **C++**: For performance-critical operations

All tools follow the same plugin interface and registration system.

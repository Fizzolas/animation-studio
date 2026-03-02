# Skinning & Weight Painting Tools

This directory contains tools for binding meshes to skeletons and painting vertex weights.

## Structure

- `binding/` - Mesh-to-skeleton binding systems
- `weight_paint/` - Weight painting brush tools
- `weight_ops/` - Weight manipulation operations
- `transfer/` - Weight transfer between meshes

## Skinning Features

### Automatic Binding
- Proximity-based automatic weights
- Heat diffusion skinning
- Geodesic distance weighting
- Bone envelope binding

### Weight Painting
- Brush-based weight painting in 3D viewport
- Variable brush size, strength, and falloff
- Add, subtract, blur, smooth weight modes
- Weight gradient tools
- Vertex selection painting
- X-mirror painting for symmetry

### Weight Operations
- Normalize weights (ensure proper distribution)
- Clean weights (remove tiny influences)
- Smooth weights (averaging with neighbors)
- Transfer weights from other meshes
- Copy/paste weights between vertices
- Invert weights
- Limit total influences per vertex

### Weight Visualization
- Color-coded weight display (gradient visualization)
- Per-bone weight isolation
- Vertex weight inspector
- Weight statistics and analysis

## Tool Plugins

Skinning tools as modular plugins:
- Weight paint brushes
- Auto-weight generators
- Weight cleanup utilities
- Mirror weight tools
- Weight transfer systems

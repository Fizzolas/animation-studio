# Format Exporters

This directory contains export handlers to external 3D and 2D file formats.

## Structure

### 3D Exporters
- `gltf/` - glTF/GLB exporter (web, game engines, AR/VR)
- `fbx/` - FBX exporter (Unity, Unreal, DCC tools)
- `obj/` - OBJ/MTL exporter (static models)
- `usd/` - USD/USDZ exporter (future - AR, high-end)
- `alembic/` - Alembic (ABC) exporter (cached animation)

### 2D Exporters
- `image/` - Image exporters (PNG, WebP, AVIF, APNG)
- `video/` - Video exporters (MP4, WebM)
- `svg/` - SVG vector exporter
- `sequence/` - Image sequence exporter

## Exporter Features

### glTF/GLB Exporter
- Optimized for real-time rendering
- Binary GLB format (single file) or JSON + bin
- PBR materials with texture packing
- Skeletal animation with skinning weights
- Morph targets / blend shapes
- Animation baking (sample rate control)
- Draco mesh compression (optional)
- Texture compression (KTX2, Basis)

### FBX Exporter
- Full animation pipeline support
- Multiple animation takes
- Skeletal rigs with bind poses
- Blend shapes and deformers
- Constraints and rig controls
- Embedded textures (optional)
- ASCII or binary FBX format
- Unity/Unreal preset optimizations

### OBJ Exporter
- Static mesh export
- Material library (MTL) generation
- Smooth groups
- Vertex colors
- Multiple objects

### Alembic Exporter
- Baked mesh animation caches
- Frame range and sample rate control
- Subdivision surface export
- Transform hierarchies
- Optimized for playback in DCCs

### Image Sequence Exporter
- Frame-by-frame rendering
- Multiple format support (PNG, WebP, AVIF, APNG)
- Alpha channel support
- Custom naming patterns
- Padding for frame numbers

### Video Exporter
- MP4 (H.264/H.265) encoding
- WebM (VP9/AV1) encoding
- Quality and bitrate control
- Audio track support (optional)
- Frame rate customization

## Export Presets

Pre-configured export settings for common targets:
- **Unity**: FBX with Unity-optimized settings
- **Unreal Engine**: FBX with Unreal conventions
- **Web (glTF)**: Compressed GLB for web viewers
- **AR (USDZ)**: Apple AR Quick Look format
- **VFX (Alembic)**: High-quality cached animation
- **Social Media**: Optimized MP4 for Instagram/Twitter

## Batch Export

- Export multiple objects to separate files
- Export multiple animation clips
- LOD (Level of Detail) generation
- Automatic texture resizing and optimization

## Quality Control

- Export validation (check for issues)
- Preview before export
- Export statistics (poly count, texture size, etc.)
- Compatibility warnings

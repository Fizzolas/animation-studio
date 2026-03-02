# Format Importers

This directory contains import handlers for external 3D and 2D file formats.

## Structure

### 3D Importers
- `gltf/` - glTF/GLB importer (geometry, materials, rigs, animation)
- `fbx/` - FBX importer (full animation pipeline support)
- `obj/` - OBJ/MTL importer (static meshes)
- `usd/` - USD/USDZ importer (future - high-end pipelines)
- `alembic/` - Alembic (ABC) importer (cached animation)
- `collada/` - COLLADA (DAE) importer

### 2D Importers
- `image/` - Raster image importers (PNG, JPEG, WebP, AVIF)
- `svg/` - SVG vector importer
- `video/` - Video frame extraction (MP4, WebM)
- `sequence/` - Image sequence importer

## Importer Features

### glTF/GLB Importer
- Meshes with multiple primitives
- PBR materials (metallic-roughness workflow)
- Node hierarchy and transforms
- Skeletal rigs (joints and inverse bind matrices)
- Skinning weights (up to 4 influences default, 8 optional)
- Morph targets / blend shapes
- Animation clips (keyframe data)
- Cameras and lights

### FBX Importer
- Mesh geometry with normals, UVs, vertex colors
- Materials (Phong, Lambert, PBR)
- Skeletal hierarchies and bind poses
- Skinning with unlimited influences
- Blend shapes and morph targets
- Multiple animation takes
- Constraints (parent, aim, orient)
- Cameras and lights
- Embedded textures

### OBJ Importer
- Mesh geometry (vertices, normals, UVs)
- Material library (MTL files)
- Multiple objects and groups
- Smooth shading groups

### Alembic Importer
- Cached mesh animation (point deformation)
- Animated transforms
- Subdivision surfaces
- Multiple time samples
- Efficient streaming of large caches

## Format Normalization

All importers convert to the internal scene representation:
- Coordinate system conversion (Y-up/Z-up handling)
- Unit scale normalization
- Material conversion to internal PBR model
- Animation curve format standardization
- Bone hierarchy normalization

## Error Handling

- Validation of file structure
- Graceful fallbacks for unsupported features
- Detailed import logs and warnings
- Preview mode (fast import for inspection)

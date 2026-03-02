# File Formats

This directory contains file format specifications and handlers for the Animation Studio.

## Structure

- `internal/` - Internal project format (.anst) specification
- `importers/` - Import handlers for external formats
- `exporters/` - Export handlers for external formats
- `converters/` - Format conversion utilities

## Internal Format (.anst)

The native Animation Studio format (.anst) is designed for:
- **Fast loading**: Chunked binary data for streaming
- **Hybrid access**: Binary data + JSON metadata
- **Versioning**: Forward and backward compatibility
- **Compression**: Optional compression for large scenes

### Format Structure
```
.anst file
├── Header (magic number, version, chunk table)
├── Metadata (JSON: scene info, layers, tool settings)
├── Geometry Chunk (binary: vertices, indices, UVs)
├── Animation Chunk (binary: curves, keyframes)
├── Materials Chunk (JSON + binary: textures, shaders)
└── Plugin State Chunk (plugin-specific data)
```

## Supported Import Formats

### 2D Formats
- **Raster**: PNG, JPEG, WebP, AVIF, APNG
- **Vector**: SVG
- **Sequence**: Image sequences (numbered files)

### 3D Formats
- **glTF/GLB**: Primary real-time format
- **FBX**: Animation-heavy pipelines
- **OBJ**: Static meshes
- **USD/USDZ**: High-end pipelines (future)

## Supported Export Formats

### 2D Exports
- **Images**: PNG, WebP, AVIF, APNG sequences
- **Video**: MP4, WebM
- **Vector**: SVG

### 3D Exports
- **glTF/GLB**: Web, game engines, AR/VR
- **FBX**: Unity, Unreal, DCC tools
- **OBJ**: Legacy and simple pipelines
- **USD/USDZ**: VFX and AR (future)

## Format Normalization

All imported formats are normalized to the internal scene representation:
- Unified coordinate system
- Consistent material model
- Standardized animation curves
- Common metadata structure

This ensures tools work identically regardless of source format.

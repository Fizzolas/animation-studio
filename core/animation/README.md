# Animation Core System

This directory contains the C++ core animation engine for high-performance animation playback and evaluation.

## Structure

- `keyframes/` - Keyframe storage and interpolation
- `curves/` - Animation curve evaluation
- `skeleton/` - Skeletal hierarchy and bone transforms
- `ik_solvers/` - High-performance IK solving algorithms
- `skinning/` - Vertex skinning and deformation
- `blendshapes/` - Blend shape / morph target system
- `constraints/` - Constraint evaluation system
- `playback/` - Animation playback and caching

## Core Components

### Keyframe System
- Efficient keyframe storage (sparse arrays)
- Multiple interpolation methods (linear, cubic, bezier)
- Keyframe evaluation and lookup
- Tangent computation for smooth curves

### Animation Curves
- Fast curve evaluation (O(log n) lookup)
- Curve caching for real-time playback
- Extrapolation modes (constant, linear, cycle)
- Curve modifiers (noise, cycles, limits)

### Skeletal System
- Hierarchical bone structure
- Local and world space transforms
- Bone matrix computation and caching
- Bone constraints evaluation

### IK Solvers
- Two-bone IK (analytical solution)
- Multi-bone IK (iterative FABRIK or CCD)
- Spline IK (bones follow curve)
- Pole vector targeting
- IK/FK blending

### Skinning Engine
- Linear blend skinning (LBS)
- Dual quaternion skinning (DQS) for better deformation
- GPU-accelerated skinning (compute shaders)
- Multi-threaded CPU skinning fallback
- Weight normalization and validation

### Blend Shape System
- Efficient blend shape evaluation
- Multiple blend shape layers
- Blend shape combination (additive/override)
- Per-vertex delta storage

### Constraint System
- Constraint graph evaluation
- Dependency resolution
- Constraint stacking and priorities
- Constraint influence blending

### Playback Engine
- Real-time animation evaluation
- Multi-threaded evaluation
- Animation result caching
- Time remapping and speed control
- Frame interpolation

## Performance Considerations

- SIMD optimization for matrix operations
- Efficient memory layout (cache-friendly)
- Lazy evaluation where possible
- GPU offloading for heavy computations
- Multi-threading support for large scenes

## Python Bindings

All core animation systems are exposed to Python via pybind11:
- Scene animation API
- Keyframe manipulation
- Curve editing
- Skeleton access
- Constraint setup

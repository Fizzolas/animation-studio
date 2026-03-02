# Animation Tools

This directory contains tools for keyframe animation, curve editing, and animation management.

## Structure

- `keyframe/` - Keyframe creation and manipulation
- `timeline/` - Timeline and dope sheet interface
- `curves/` - Animation curve editor and graph editor
- `nla/` - Non-linear animation (action blending)
- `pose_mode/` - Character pose and animation tools
- `motion/` - Motion paths and trajectory visualization
- `deformers/` - Shape keys, lattices, and mesh deformers

## Animation Features

### Keyframe System
- Keyframe any animatable property (location, rotation, scale, custom)
- Auto-keyframing toggle
- Keyframe interpolation (linear, bezier, constant, bounce, elastic)
- Keyframe snapping and alignment
- Copy/paste keyframes
- Bake animation (convert procedural to keyframes)

### Timeline & Dope Sheet
- Visual timeline with frame scrubbing
- Multi-object keyframe overview
- Keyframe selection and manipulation
- Timeline markers and labels
- Frame range and playback controls
- Speed ramping and time remapping

### Curve Editor / Graph Editor
- Detailed animation curve visualization
- Bezier tangent handle editing
- Curve smoothing and simplification
- Mathematical curve modifiers (noise, cycles, limits)
- Curve extrapolation (constant, linear, cyclic)
- Frame/value snapping

### Non-Linear Animation (NLA)
- Layer multiple animation clips
- Blend and crossfade between actions
- Action strips with timing control
- Influence and weight adjustment
- Action scaling and repetition

### Pose Mode (Character Animation)
- Dedicated mode for posing rigged characters
- Pose library (save/load common poses)
- Pose-to-pose animation workflow
- Breakdowns and in-betweens
- Pose mirroring (left/right symmetry)
- Auto IK for easier posing

### Motion Visualization
- Motion paths showing object trajectories
- Onion skinning (ghost frames before/after)
- Frame number overlays
- Velocity and acceleration visualization

### Deformation Systems
- **Shape Keys / Blend Shapes**: Morph target animation for faces
- **Lattice Deformation**: Cage-based mesh deformation
- **Mesh Deformers**: Wrap, surface, and cage deformers
- **Modifiers**: Subdivision, mirror, array applied to animation

## Tool Plugins

Animation tools as extensible plugins:
- Custom keyframe tools
- Specialized curve editors
- Animation layers
- Motion capture import/retargeting
- Procedural animation helpers (noise, oscillators)

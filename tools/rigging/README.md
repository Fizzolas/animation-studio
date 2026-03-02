# Rigging Tools

This directory contains tools for creating and manipulating 3D character rigs.

## Structure

- `armature/` - Bone creation and skeleton management
- `ik_fk/` - Inverse kinematics and forward kinematics solvers
- `constraints/` - Constraint systems (parent, target, track-to, etc.)
- `controls/` - Custom rig control shapes and widgets
- `pose/` - Pose library and pose management
- `auto_rig/` - Automatic rigging systems

## Core Rigging Features

### Armature System
- Create and edit bone hierarchies
- Bone roll and orientation control
- Bone parenting and relationships
- Bone layers for organization
- Symmetrical editing (X-mirror)

### IK/FK Systems
- IK chain solvers (standard, pole target, spline IK)
- FK rotation chains
- IK/FK switching and blending
- Pole vector targets
- Stretch/squash for IK chains

### Constraints
- Parent constraint (follow parent transforms)
- Target constraint (aim at target)
- Track-to constraint (rotation tracking)
- Copy location/rotation/scale
- Limit location/rotation/scale
- Floor constraint (prevent penetration)
- Damped track, locked track
- Child of constraint

### Rig Controls
- Custom control shapes (circles, boxes, arrows)
- Control color coding
- Control scaling and visibility
- Control parenting and hierarchy

## Tool Plugins

All rigging tools are plugins that can be extended or replaced:
- Bone creation tools
- IK/FK setup wizards
- Auto-rig generators (biped, quadruped, etc.)
- Constraint setup helpers
- Rig validation tools

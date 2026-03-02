# Scripting System

This directory contains the integrated scripting environment for on-the-go tool creation and workflow automation.

## Structure

- `console/` - Embedded scripting console panel
- `api/` - Python scripting API exposed to users
- `stdlib/` - Standard library of scripting utilities
- `examples/` - Example scripts and tutorials
- `sandbox/` - Script execution sandbox

## Scripting Capabilities

### Scene Manipulation
- Access nodes, transforms, materials
- Modify animation curves and keyframes
- Create and delete objects
- Query selection and hierarchy

### Tool Creation
- Define custom tools that appear in tool palette
- Register keyboard shortcuts and menu items
- Create custom UI panels and widgets
- Hot-reload tool definitions

### Workflow Automation
- Batch operations on multiple objects
- Procedural animation helpers
- Custom export pipelines
- Automated rigging and constraints

## API Design

The scripting API provides:
- **High-level scene access**: Simple, Pythonic interface
- **Type safety**: Clear types and validation
- **Documentation**: Inline help and autocomplete
- **Safety**: Sandboxed execution with restricted operations

## Example Scripts

```python
import animation_studio as ast

# Get selected objects
selection = ast.scene.get_selection()

# Create animation curve
for obj in selection:
    curve = obj.add_animation('position.y')
    curve.add_keyframe(0, 0.0)
    curve.add_keyframe(24, 5.0)
    curve.add_keyframe(48, 0.0)
    curve.set_interpolation('smooth')
```

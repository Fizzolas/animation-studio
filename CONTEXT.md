# Animation Studio - Project Context

## Vision
An open-source animation suite designed for simplicity and accessibility. Create anything from 2D drawings to complex 3D model animation and renders through an intuitive, comfortable interface.

## Core Philosophy
- **Simple to Use**: Tools are easy to find and understand, even for beginners
- **Fully Open Source**: Every component can be modified, extended, or replaced
- **Modular Architecture**: Workshop-based system for sharing and adding community tools
- **Comfortable UI**: Soft design with clear organization through folders and layers

## Inspiration
Drawing from creation studios like Roblox Studio and Garry's Mod, this project aims to democratize animation by making professional-quality tools accessible to everyone.

## Key Features

### Animation Capabilities
- **2D Drawing Tools**: Sketch, paint, and animate in 2D space
- **3D Model Animation**: Full character animation pipeline with rigging, skinning, and keyframe animation
- **3D Effects & Rendering**: Complete 3D workflow with modeling, effects, and rendering
- **Timeline & Keyframes**: Industry-standard animation timeline with keyframe editing for both 2D and 3D
- **Layer System**: Organize work across multiple layers with folder grouping

### Modular Tool System
- **Plugin Architecture**: Every tool is a plugin that can be replaced or modified
- **Workshop Integration**: Public workshop for sharing custom tools and extensions
- **Hot-Swappable Tools**: Add, remove, or update tools without restarting
- **Tool Categories**: Organized by function (drawing, modeling, rigging, animation, effects, rendering, etc.)

### User Interface
- **Soft, Modern Design**: Comfortable aesthetic that's easy on the eyes
- **Folder/Layer Organization**: Hierarchical structure for managing complex projects
- **Customizable Layout**: Drag-and-drop panels to create your ideal workspace
- **Searchable Tools**: Quick search to find any tool instantly
- **Contextual Menus**: Right-click anywhere for relevant options

## Technical Stack (To Be Determined)
- Core engine and rendering pipeline
- UI framework for comfortable, responsive interface
- Plugin system architecture
- File format for projects and animations
- Workshop/marketplace system for tool distribution

## Project Structure
```
animation-studio/
├── core/           # Core engine and systems
├── ui/             # User interface components
├── tools/          # Built-in tool plugins
├── plugins/        # Plugin system architecture
├── workshop/       # Workshop integration
├── scripting/      # Integrated scripting environment
├── formats/        # File format handlers
├── docs/           # Documentation
└── examples/       # Example projects and tutorials
```

## Development Roadmap

### Phase 1: Foundation
- [ ] Core architecture design
- [ ] Basic UI framework
- [ ] Plugin system implementation
- [ ] Simple 2D drawing tools

### Phase 2: 2D Capabilities
- [ ] Complete 2D toolset
- [ ] Animation timeline
- [ ] Layer management
- [ ] Basic export functionality

### Phase 3: 3D Integration
- [ ] 3D viewport with real-time preview
- [ ] 3D modeling tools (primitives, extrude, loop cut, subdivision)
- [ ] Character rigging system (bones, IK/FK, constraints)
- [ ] Skinning and weight painting tools
- [ ] 3D animation keyframing and curve editor
- [ ] 3D rendering pipeline with PBR materials
- [ ] 2D/3D workflow integration

### Phase 4: Workshop & Community
- [ ] Workshop system
- [ ] Tool sharing/distribution
- [ ] Community examples
- [ ] Documentation and tutorials

## Contributing
This is an open-source project welcoming contributions of all kinds:
- Code contributions (features, bug fixes)
- Tool plugins and extensions
- Documentation improvements
- UI/UX design
- Testing and feedback

## License
MIT License - fully open source with permissive licensing to encourage community growth and tool development.

## Getting Started
Detailed setup instructions will be added as the project develops. For now, watch this repository for updates and join discussions in Issues.

---

## Complete 3D Animation Pipeline

### 3D Model Animation Tools

The suite provides a complete pipeline for 3D character and object animation, comparable to professional DCC tools.

#### Rigging System
- **Armature/Skeleton Creation**: Create bone hierarchies for character rigs
- **IK/FK Systems**: Inverse kinematics and forward kinematics with seamless switching
- **Constraints**: Parent, target, track-to, copy transforms, limit rotation/location/scale
- **Custom Rig Controls**: Create custom controller shapes and UI for animators
- **Bone Layers**: Organize bones by function (deform, control, mechanics)
- **Pose Library**: Save and reuse common poses

#### Skinning & Weight Painting
- **Automatic Skinning**: Initial weight assignment based on bone proximity
- **Weight Painting**: Visual weight painting with brush-based tools
- **Weight Transfer**: Copy weights from reference meshes
- **Mirror Weights**: Symmetrical weight editing for characters
- **Normalize Weights**: Ensure proper weight distribution

#### Animation Tools
- **Keyframe Animation**: Set keyframes on any animatable property (transforms, shapes, materials)
- **Curve Editor**: Detailed control over animation curves with tangent handles
- **Dope Sheet**: Timeline overview for managing keyframes across objects
- **Graph Editor**: Fine-tune animation timing and interpolation
- **Non-linear Animation (NLA)**: Layer and blend multiple animation clips
- **Action Editor**: Manage multiple animation takes per object

#### Character Animation Features
- **Pose Mode**: Dedicated mode for posing and animating rigged characters
- **Auto-Keyframing**: Automatically create keyframes when moving objects
- **Onion Skinning**: View previous/next frames for animation reference (2D and 3D)
- **Motion Paths**: Visualize object trajectories over time
- **Grease Pencil Integration**: Draw 2D animation notes directly in 3D viewport

#### Advanced Animation Systems
- **Shape Keys/Blend Shapes**: Morph target animation for facial expressions
- **Lattice Deformation**: Non-destructive mesh deformation
- **Mesh Deformers**: Cage deformers, wrap deformers, surface deformers
- **Simulation**: Cloth, soft body, and rigid body physics for secondary motion
- **Particle Systems**: Hair, fur, and particle effects

### 3D Viewport & Visualization
- **Multiple Shading Modes**: Wireframe, solid, material preview, rendered
- **Real-time Lighting**: Preview lighting setup in viewport
- **Bone Display Options**: Octahedral, stick, envelope, custom shapes
- **X-Ray Mode**: See-through display for rigging and weight painting
- **Gizmos**: Visual transform gizmos for precise manipulation

---

## Advanced Architecture & Formats

### Supported 2D Formats (Import/Export)

The suite should support both raster and vector 2D content so artists can bring in assets from anywhere and export to web, video, or game engines.

- **Raster images**: JPEG, PNG, WebP, AVIF, and APNG for high-quality animated sprites and sequences (PNG/APNG for transparency, WebP/AVIF for small and efficient files)
- **Vector graphics**: SVG as the primary scalable vector format, allowing resolution-independent UI elements, rig controls, and line-art animation
- **Video-style exports**: MP4/WebM as recommended options for longer animations, since traditional animated image formats (like GIF) are large and visually limited compared to video

Internally, 2D timelines should store keyframes, layer data, and effects in a structured scene format, with importers/exporters converting to these external formats as needed.

### Supported 3D Formats (Import/Export)

For 3D, the suite should balance "accept everything" with a focused set of optimized, well-supported formats.

- **Core real-time format**: glTF/GLB as the "JPEG of 3D" for compact, fast-loading models with PBR materials and animation, ideal for real-time rendering and interactive previews
- **Animation-heavy pipelines**: FBX for complex character rigs, skeletal animation, blend shapes, and rich animation data to integrate well with game engines like Unity/Unreal and DCC tools like Maya and 3ds Max
- **Static / legacy models**: OBJ as a widely compatible fallback for static meshes and simple assets
- **High-end / collaborative pipelines (future)**: USD/USDZ as a target for large, layered, non-destructive scenes and high-end VFX/AR pipelines where complex hierarchies and variants are needed
- **Alembic (ABC)**: For cached animation data, particularly cloth and simulation results

The engine should normalize all imported formats into a single internal scene representation (geometry, materials, rigs, skeletal hierarchies, animation curves, blend shapes, metadata) so tools work consistently regardless of original file type.

### Hybrid Performance Architecture

#### Fast Core + Python Orchestration

The application should follow a hybrid architecture: performance-critical work in a native language (e.g., C++), with Python used as a high-level scripting and extension layer.

- **Native core**: Core rendering, playback, physics, deformation, skeletal animation, IK solving, and heavy data transforms should live in a compiled C++ (or similar) core to maintain real-time performance for complex 2D/3D scenes
- **Python layer**: Python should orchestrate tools, define workflows, manage UI interactions and plugins, and call into the native core via bindings (e.g., pybind-style interoperability) so that slow paths are minimized but rapid development remains possible
- **Interchangeable implementations**: Where possible, critical subsystems may have both Python and native implementations, with data formats designed so that either implementation can read/write the same files and continue each other's work

This design keeps the "feel" of a responsive, native animation tool, while allowing rapid iteration and a rich ecosystem of Python-based tools and scripts.

#### Engine-Python Boundary and API Design

To keep the hybrid model maintainable:

- The core should expose a clear, versioned API to Python for scene access (nodes, transforms, materials, bones, animation curves, blend shapes), tool invocation, and playback control
- Data passed across the boundary should use compact, predictable structures (e.g., tightly packed arrays/buffers for geometry, bone matrices, and animation curves, simple objects/IDs for scene graph references) to minimize marshaling overhead
- Long-running or high-frequency operations (real-time playback, IK solvers, physics, skeletal deformation, heavy modifiers) must remain inside the native core, with Python only sending parameters and receiving results, not per-frame bulk data

### Integrated Scripting and Tooling Workspace

#### Scripting Panel and Live Tools

The suite should include a dedicated scripting environment to let users build "on-the-go" tools and workflow helpers.

- **Embedded scripting console**: A dockable panel for writing and running scripts directly in the UI, with access to the scene API, selection, timelines, and file operations
- **Tool scripts**: Scripts can define new tools (brush variants, selection helpers, batch exporters, auto-rigging helpers, constraint setups, procedural effects) that appear in the main tool palette once registered
- **Live reloading**: Scripts and tool definitions should reload without restarting the whole application, enabling rapid iteration and experimentation
- **Sandboxing and safety**: The scripting API should restrict dangerous operations and clearly separate "editor automation" from low-level engine internals

These scripts would often be Python, but the internal architecture should remain open enough that other scripting languages could be added in the future through the same plugin model.

#### Workflow Helpers and Automation

The scripting system should make it easy to automate repetitive work:

- Batch operations (renaming, retargeting animation between rigs, re-baking animation, mass export to multiple formats like FBX/GLB/PNG/WebM)
- Procedural animation helpers (noise layers, oscillators, constraints to drive 2D rigs or 3D controllers)
- Auto-rigging systems (procedural rig generation from mesh analysis)
- Custom UI widgets and mini-panels for specific pipelines, built using the same scripting API used for tools

### File Design for Speed and Interop

#### Internal Scene and Animation Format

Internally, the project should use a compact, structured scene format optimized for both fast native access and safe scripting:

- **Binary core data**: Geometry, skeletal hierarchies, bone transforms, animations, blend shapes, and other heavy data should be stored in binary blobs or chunked data structures that map efficiently into native memory for the C++ core, similar in spirit to glTF/GLB's compact binary representation
- **Metadata and scripting layer**: Higher-level metadata (layer names, tags, tool settings, plugin state, rig control metadata) can live in a readable, versioned structure (e.g., JSON-like or similar), making it easy for Python tools to inspect and modify without touching heavy data
- **Chunked/streaming support**: Large scenes should be loadable in chunks so that playback and editing can start before the entire file is loaded, inspired by real-time-oriented formats that support progressive loading

#### External Export Strategy

For interoperability with other tools and engines, the application should adopt a multi-format export strategy tailored to different targets:

- **Real-time and web**: Export GLB/GLTF with baked animations, skeletal rigs, and PBR materials for game engines, web viewers, and AR/VR
- **Game and DCC pipelines**: Export FBX for complex character animation pipelines with rigs, skinning, blend shapes, and multiple animation takes in Unity, Unreal, and Autodesk tools
- **Cached animation**: Export Alembic (ABC) for baked mesh animation, particularly for cloth simulation and deformation caches
- **Static models**: Export OBJ and high-quality textures for simple or legacy pipelines
- **High-end pipelines**: Export USD/USDZ for large, collaborative productions and AR-heavy workflows where that ecosystem is already in place
- **2D outputs**: Export image sequences (PNG, WebP, AVIF, APNG) and videos (MP4/WebM) so users can choose between quality and file size for delivery

The exporter layer should be modular so that community plugins can add new formats or customize export presets without modifying the core.

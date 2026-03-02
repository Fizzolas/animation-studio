# Animation Studio - Project Context

## Vision
An open-source animation suite designed for simplicity and accessibility. Create anything from 2D drawings to complex 3D effects and renders through an intuitive, comfortable interface.

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
- **3D Effects & Rendering**: Full 3D workflow with modeling, effects, and rendering
- **Timeline & Keyframes**: Industry-standard animation timeline with keyframe editing
- **Layer System**: Organize work across multiple layers with folder grouping

### Modular Tool System
- **Plugin Architecture**: Every tool is a plugin that can be replaced or modified
- **Workshop Integration**: Public workshop for sharing custom tools and extensions
- **Hot-Swappable Tools**: Add, remove, or update tools without restarting
- **Tool Categories**: Organized by function (drawing, modeling, effects, rendering, etc.)

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
- [ ] 3D viewport
- [ ] Basic modeling tools
- [ ] 3D rendering pipeline
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
To be determined - will be fully open source with permissive licensing to encourage community growth and tool development.

## Getting Started
Detailed setup instructions will be added as the project develops. For now, watch this repository for updates and join discussions in Issues.


You’re asking for three big additions to the project definition: fully flexible import/export, a built‑in scripting system, and a hybrid “fast core + Python glue” architecture with file formats that support that goal. Since I can’t modify the repo directly right now, I’ll draft text you can append to the end of CONTEXT.md. You can paste this under a new heading like “Advanced Architecture & Formats”.

Advanced Import/Export and Formats
Supported 2D Formats (Import/Export)
The suite should support both raster and vector 2D content so artists can bring in assets from anywhere and export to web, video, or game engines.

Raster images: JPEG, PNG, WebP, AVIF, and APNG for high‑quality animated sprites and sequences (PNG/APNG for transparency, WebP/AVIF for small and efficient files).

Vector graphics: SVG as the primary scalable vector format, allowing resolution‑independent UI elements, rig controls, and line‑art animation.
​

Video‑style exports: MP4/WebM as recommended options for longer animations, since traditional animated image formats (like GIF) are large and visually limited compared to video.

Internally, 2D timelines should store keyframes, layer data, and effects in a structured scene format, with importers/exporters converting to these external formats as needed.

Supported 3D Formats (Import/Export)
For 3D, the suite should balance “accept everything” with a focused set of optimized, well‑supported formats.

Core real‑time format: glTF/GLB as the “JPEG of 3D” for compact, fast‑loading models with PBR materials and animation, ideal for real‑time rendering and interactive previews.

Animation‑heavy pipelines: FBX for complex character rigs and rich animation data, to integrate well with game engines like Unity/Unreal and DCC tools like Maya and 3ds Max.

Static / legacy models: OBJ as a widely compatible fallback for static meshes and simple assets.

High‑end / collaborative pipelines (future): USD/USDZ as a target for large, layered, non‑destructive scenes and high‑end VFX/AR pipelines where complex hierarchies and variants are needed.

The engine should normalize all imported formats into a single internal scene representation (geometry, materials, rigs, animation curves, metadata) so tools work consistently regardless of original file type.

Hybrid Performance Architecture
Fast Core + Python Orchestration
The application should follow a hybrid architecture: performance‑critical work in a native language (e.g., C++), with Python used as a high‑level scripting and extension layer.

Native core: Core rendering, playback, physics, deformation, and heavy data transforms should live in a compiled C++ (or similar) core to maintain real‑time performance for complex 2D/3D scenes.

Python layer: Python should orchestrate tools, define workflows, manage UI interactions and plugins, and call into the native core via bindings (e.g., pybind‑style interoperability) so that slow paths are minimized but rapid development remains possible.

Interchangeable implementations: Where possible, critical subsystems may have both Python and native implementations, with data formats designed so that either implementation can read/write the same files and continue each other’s work.
​
​

This design keeps the “feel” of a responsive, native animation tool, while allowing rapid iteration and a rich ecosystem of Python‑based tools and scripts.

Engine–Python Boundary and API Design
To keep the hybrid model maintainable:

The core should expose a clear, versioned API to Python for scene access (nodes, transforms, materials, animation curves), tool invocation, and playback control.

Data passed across the boundary should use compact, predictable structures (e.g., tightly packed arrays/buffers for geometry and animation curves, simple objects/IDs for scene graph references) to minimize marshaling overhead.

Long‑running or high‑frequency operations (real‑time playback, IK solvers, physics, heavy modifiers) must remain inside the native core, with Python only sending parameters and receiving results, not per‑frame bulk data.

Integrated Scripting and Tooling Workspace
Scripting Panel and Live Tools
The suite should include a dedicated scripting environment to let users build “on‑the‑go” tools and workflow helpers.

Embedded scripting console: A dockable panel for writing and running scripts directly in the UI, with access to the scene API, selection, timelines, and file operations.

Tool scripts: Scripts can define new tools (brush variants, selection helpers, batch exporters, auto‑rigging helpers, constraint setups, procedural effects) that appear in the main tool palette once registered.

Live reloading: Scripts and tool definitions should reload without restarting the whole application, enabling rapid iteration and experimentation.

Sandboxing and safety: The scripting API should restrict dangerous operations and clearly separate “editor automation” from low‑level engine internals.

These scripts would often be Python, but the internal architecture should remain open enough that other scripting languages could be added in the future through the same plugin model.

Workflow Helpers and Automation
The scripting system should make it easy to automate repetitive work:

Batch operations (renaming, retargeting, re‑baking animation, mass export to multiple formats like FBX/GLB/PNG/WebM).

Procedural animation helpers (noise layers, oscillators, constraints to drive 2D rigs or 3D controllers).

Custom UI widgets and mini‑panels for specific pipelines, built using the same scripting API used for tools.

File Design for Speed and Interop
Internal Scene and Animation Format
Internally, the project should use a compact, structured scene format optimized for both fast native access and safe scripting:

Binary core data: Geometry, animations, and other heavy data should be stored in binary blobs or chunked data structures that map efficiently into native memory for the C++ core, similar in spirit to glTF/GLB’s compact binary representation.

Metadata and scripting layer: Higher‑level metadata (layer names, tags, tool settings, plugin state) can live in a readable, versioned structure (e.g., JSON‑like or similar), making it easy for Python tools to inspect and modify without touching heavy data.

Chunked/streaming support: Large scenes should be loadable in chunks so that playback and editing can start before the entire file is loaded, inspired by real‑time‑oriented formats that support progressive loading.

External Export Strategy
For interoperability with other tools and engines, the application should adopt a multi‑format export strategy tailored to different targets:

Real‑time and web: Export GLB/GLTF with baked animations and PBR materials for game engines, web viewers, and AR/VR.

Game and DCC pipelines: Export FBX for complex character animation pipelines in Unity, Unreal, and Autodesk tools.

Static models: Export OBJ and high‑quality textures for simple or legacy pipelines.

High‑end pipelines: Export USD/USDZ for large, collaborative productions and AR‑heavy workflows where that ecosystem is already in place.

2D outputs: Export image sequences (PNG, WebP, AVIF, APNG) and videos (MP4/WebM) so users can choose between quality and file size for delivery.

The exporter layer should be modular so that community plugins can add new formats or customize export presets without modifying the core.

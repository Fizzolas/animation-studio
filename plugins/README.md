# Plugin System

This directory contains the plugin architecture that enables the modular tool system.

## Structure

- `api/` - Plugin API definitions and interfaces
- `registry/` - Plugin discovery and registration system
- `loader/` - Dynamic plugin loading and hot-reloading
- `manager/` - Plugin lifecycle management
- `templates/` - Plugin templates for developers

## Plugin Architecture

The plugin system supports:

### Plugin Types
- **Tool Plugins**: Drawing, modeling, animation tools
- **Import/Export Plugins**: File format handlers
- **Effect Plugins**: Visual effects and modifiers
- **UI Plugins**: Custom panels and widgets
- **Script Plugins**: Python-based automation

### Features
- **Hot-Swapping**: Add/remove plugins without restart
- **Version Control**: Plugin API versioning
- **Dependency Management**: Plugin dependencies and conflicts
- **Sandboxing**: Safe execution environment

## Developing Plugins

Plugin development guides and templates will be added to the documentation.

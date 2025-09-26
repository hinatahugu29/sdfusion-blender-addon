# SDFusion

![Blender Logo](https://upload.wikimedia.org/wikipedia/commons/thumb/0/0c/Blender_logo_no_text.svg/512px-Blender_logo_no_text.svg.png)  
An intuitive toolkit for SDF-like, non-destructive boolean modeling, and mirror operations. This addon helps you manage complex boolean setups with a simple layer-based workflow, from rapid prototyping to final mesh generation.

## Features
- **Layer-based Boolean Management**: Non-destructive ADD/SUB operations with Remesh modifier for SDF-like results.
- **Live Controls**: Real-time voxel size and smoothing adjustments.
- **Mirror Operations**: Easy symmetric modeling with origin objects.
- **Finalize Tools**: Apply all modifiers, organize cutters, and cleanup.
- **Asset Integration**: Built-in installer for SDFusion asset libraries (Blender 4.0+).

Supports Blender **4.5.0+**. Licensed under [GPL-3.0-or-later](LICENSE).

## Installation
1. Download the addon ZIP from [Releases](https://github.com/あなたのユーザー名/sdfusion-blender-addon/releases).
2. In Blender: `Edit > Preferences > Add-ons > Install...` → Select the ZIP.
3. Enable "SDFusion" in the Add-ons list.
4. Access via `View3D > Sidebar (N) > SDFusion`.

### Asset Installation
- In Add-on Preferences: Click "Install Assets..." to extract and register the asset library.
- Default path: `~/Documents/Blender Assets/SDFusion Assets`.

## Usage
1. Select a mesh object and click **Reset** to initialize layers.
2. Assign objects to **ADD/SUB Layers** via the panel.
3. Adjust **Live Controls** for preview.
4. Use **Mirror** for symmetry.
5. **Finalize** to apply and export the result.

![Screenshot Placeholder](path/to/screenshot.png)  
*(Add screenshots of the panel and workflow here for better visualization.)*

## Tags
Modeling, Object, Boolean, SDF, Non-destructive, Hard Surface

## Contributing
- Fork the repo and submit a PR.
- Report issues [here](https://github.com/あなたのユーザー名/sdfusion-blender-addon/issues).

## Maintainer
[hinata_hugu](https://github.com/hinata_hugu) (original author)

Built with ❤️ using Blender Python API.

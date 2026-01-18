# Collection Object Walker

**Collection Object Walker** is a companion add-on bundled with SDFusion. It allows you to preview objects in a collection one at a time, making it easy to browse and select cutter shapes for your Boolean operations.

## Overview

When working with SDFusion, you may create a library of reusable cutter objects. Collection Object Walker helps you:

- **Preview cutters one by one** - Quickly cycle through objects to find the right shape
- **Compare shapes visually** - Only the current object is visible, making comparison easy
- **Manage display types** - Switch between Solid, Wire, Bounds, or Textured views

## Installation

Collection Object Walker is included with your SDFusion purchase. Install it separately in Blender:

1. Download the `CollectionObjectWalker_x_x_x.zip` from your purchase
2. In Blender: `Edit` → `Preferences` → `Add-ons`
3. Click `Install...` and select the ZIP file
4. Enable "Collection Object Walker" in the add-on list

## User Interface

The panel is located in the **3D Viewport Sidebar** under the `CollWalker` tab.

### Panel Sections

| Section | Description |
|---------|-------------|
| **Target** | Select the collection to browse. Use the eyedropper or "Set from Active" button. |
| **Display Type** | Choose how objects are displayed (Bounds/Wire/Solid/Textured). |
| **Walker** | Navigate through objects with Prev/Next buttons. Shows current index and object name. |
| **Batch Operations** | Bulk visibility controls for viewport and render. |

## How to Use

### Basic Workflow

1. **Prepare a Cutter Collection**
   - Create a collection (e.g., `Cutter_Library`)
   - Add your reusable cutter objects to this collection

2. **Open Collection Walker**
   - Press `N` to open the sidebar
   - Switch to the `CollWalker` tab

3. **Select Target Collection**
   - Click the collection dropdown and choose your cutter library
   - Or use the eyedropper icon to pick from the 3D viewport
   - Or select an object and click the "Set from Active" button

4. **Browse Cutters**
   - Click `< Prev` or `Next >` to cycle through objects
   - Only the current object is visible; others are hidden
   - The object name and index are displayed (e.g., "3 / 10")

5. **Apply to SDFusion**
   - When you find the cutter you want, it's already selected
   - Use SDFusion's layer panel to add it as a Boolean cutter

### Tips

- **Exclude Empties**: Enable this option to skip Empty objects in the walker
- **Apply to All**: Set the display type for all objects in the collection at once
- **Reset (Show All)**: Unhide all objects when you're done browsing

## Workflow with SDFusion

```
┌─────────────────────────────────────────────────────┐
│  Collection: "Cutter_Library"                       │
│  ├── Cutter_Star                                    │
│  ├── Cutter_Heart      ◀── Browse with Walker       │
│  ├── Cutter_Diamond                                 │
│  └── Cutter_Custom                                  │
└─────────────────────────────────────────────────────┘
                    ↓
         Found the perfect cutter!
                    ↓
         Add to SDFusion as SUB layer
                    ↓
         Non-destructive Boolean applied!
```

This workflow is especially useful when:
- You have many custom cutter shapes
- Cutter names don't clearly describe the shape
- You want to visually compare options before committing

---

<span style="font-size: 20px;">Back: [How to Use](how_to_use.md) | [Home](index.md)</span>

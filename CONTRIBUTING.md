# Contributing to Kerb Kit
We recommend starting with the [README](README.md) for a big-picture look at what Kerb Kit is and how it supports the OpenStreetMap community. For general design guidance, see: [Design Guidance](/DESIGN_GUIDANCE.md).

## How the Asset Workflow Works

1. **You submit individual SVG files.** Each file should represent a single element (e.g., `kerb=lowerd.svg`) exported as plain SVG and aligned to the standard grid.
2. **We review, clean, and organize submissions.** Submissions are reviewed for visual clarity, tagging alignment, and design consistency. Approved assets are added to the library.
3. **We maintain separate design files.** For convenience, we keep Affinity Designer files in a Google Drive folder to help get new illustrations rolling. If you use Affinity Designer, you may find this helpful as a reference. You do not need to work in Affinity Designer to contribute. (see: [Google Drive](https://drive.google.com/drive/folders/1u9iJec_ZKIN5SV3JdG4HeA_tUl_8QvcY?usp=sharing))
4. **You can browse and reuse tiles.** Feel free to reuse tiles in new illustrations.

## Project Structure

### The Graphics Library (`library/`)

Each folder in the library contributes assets along a specific theme. Within each **library folder** you find **asset folders** named according to the asset type: example scenes, annotations, map features, or features of the pedestrian environment.

Subfolders:
- `shared/` This is a where we keep visual components, utilities, and references that are reused across **multiple themes**.
- `<theme>/` Adds assets to the library along a coherent *theme*.
  - `annotations/`
    - `arrow.svg`
    - `box.svg`
  - `environment/`
    - `physical-thing.svg`
  - `map-features/`
    - `special-node-style.svg`
  - `templates/`
    - `example-scene-001.svg`
    - `example-scene-002.svg`
  - `README.md` instructions or examples showcasing the theme

## Asset Types

> [!TIP]
> **These Terms May Change**, here is how you can help:
> - Review these definitions and suggest improvements or refinements
> - Share examples or counter-examples if something feels ambiguous

To support contributors and maintain clarity as the project progresses, we've defined a shared vocabulary for the types of visual assets used. While not every definition dictates a strict folder layout, many do imply a consistent structure.

**🛠️ After all, we're laying the groundwork** for a system that's easy to navigate, extend, and maintain.

This shared language helps everyone understand how the pieces fit together conceptually, whether you're creating assets, assembling scenes, or writing documentation.

### **Environmental Features**

> **Definition:** Physical, real-world elements present in the built environment. These include the things you would observe if standing at the location.

Examples:

- Curbs (flush, raised, lowered, etc.)
- Sidewalks
- Roads and road markings
- Ramps
- Pedestrian islands
- Tactile paving

### **Map Features**

> **Definition:** Abstract representations of how OpenStreetMap encodes physical space and infrastructure. These are typically invisible in real life but critical for tagging and data structure.

Examples:

- Nodes (points)
- Ways (lines)
- Areas (closed polygons)

### **Annotations**

> **Definition:** Explanatory visual aids layered on top of scenes to clarify meaning, highlight tagging logic, or walk the viewer through a diagram.

Examples:

- Callout lines and text
- Highlight bubbles or arrows

### **Templates (or Scene-Templates)**

> **Definition:** Pre-built diagram scenes combining multiple elements for reuse or customization. Templates serve as starting points for creating scenes that support education, outreach, or documentation.

Examples:

- A residential street with an unmarked crossing and a lowered curb
- A street with a crossing island
- A marked crossing with traffic signals
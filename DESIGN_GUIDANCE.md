# Kerb Kit Design Guidance

Consistent, modular assets help everyone build diagrams and scenes quickly—no matter where or how they use Kerb Kit. This guide explains how to design new illustrations and assets so they harmonize with the kit and each other.

## The Design Environment

When creating new artwork for the Kerb Kit Library, you can use any tool that you prefer. The only requirement of the tool is that it can produce compliant SVGs (see: [File Format & Export Settings](#file-format--export-settings)).

### Isometric Perspective & Baseline Grid

- **All Kerb Kit assets use a 2:1 isometric projection** (see: [wiki](https://en.wikipedia.org/wiki/Isometric_projection)), giving a sense of depth and spatial relationships.
- **Baseline grid:** Assets are aligned to a 1x1x1 yard cube (isometric).
    - This cube is your primary building block for most features (e.g., a curb, slab, or paving stone).
    - To create smaller details, subdivide the cube into smaller fractions (1/2, 1/3rd, or 1/6th).
    - For larger features (e.g., intersections), use a multiple of the cube (2x1, 3x1, etc.).
- **Snap everything to the grid:** This ensures tiles and assets will align seamlessly when assembled.

Tiles designed on a true isometric grid don't easily (or intuitively) align with each other on a standard grid. Switching to a 2:1 version of isometric projection (slightly squashed from true isometric) can help isometric tiles to align onto a standard grid, once they're flattened and scaled appropriately. The following grids and grid settings to help streamline the workflow during the design process so that tiles align nicely for users.

### The Tile Design: 36px Standard Grid

![tile design grid](/docs/static/tile_design_grid.jpg)

- Used by: Tile Designers
- Scale: 36px = 36 in = 1 yd
- Baseline Grid Spacing: 36px
- Grid Divisions: 6

This grid allows artists to layout their work on flat surfaces without any projection added. Depending on your editing software, you can convert the faces into symbols that you'll use in your isometric projection, allowing you to get the benefit of seeing your tiles simultaneously in both the projected and unprojected views.

> *As of now, in my workflow, I'm building the look of my tiles here as separate faces before assembling them during the projection step.* -- @thompsondt

### Tile Projection: 40.2px 2-to-1 Isometric Grid

- Used by: Tile Designers
- Grid Spacing: 40.2px
- Grid Divisions:

![tile projection grid](/docs/static/tile_isometric_grid.jpg)

While acceptable isometric illustrations can be designed with careful use of a flat grid, working in an editor that directly supports a 2:1 isometric projection adds a fair amount of convenience and flexibility. The grid spacing is a little different in this step: 40.2px vs 36px in the previous step. That can feel a little weird, but the math works out so that the tiles will snap together nicely in the next step.

> [!NOTE]
> Export your work from the isometric grid and then test loading that work on the standard grid, as a library user would.

### Tile Placement: 36px Standard Grid

- Used by: Library Users
- Grid Spacing: 36px
- Grid Divisions: 6

![tile placement grid](/docs/static/tile_place_grid.jpg)

Library users will snap together the "flattened" SVGs on a 36px square grid (the standard grid). The tiles retain their 3D perspective and the alignment grid only *appears* isometric.

## File Format & Export Settings

Create and submit assets as plain SVG files.
- **Name files descriptively and in kebab-case**, e.g., `kerb-lowered.svg`, `intersection-2x2.svg`.
- Remove editor metadata and unnecessary groups.

<!-- not concerned with optimization at this stage of development
- Optimize using tools like [SVGOMG](https://jakearchibald.github.io/svgomg/) or [SVGO](https://github.com/svg/svgo).
-->

Affinity Designer Settings:

| Option                | Setting                 | Function                                                                                                                 | Rationale                                                                                                                                                                        |
| --------------------- | ----------------------- | ------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Rasterize             | Nothing                 | How to handle design elements that are supported by the SVG format. Rasterization would turn these elements into pixels. | Nothing should be rasterized so that we can directly inspect changes in the SVGs. It might be reasonable to link images as external files. If that interests you, let's discuss. |
| Resolution            | Use document resolution | Even if not rasterizing anything, this still impacts the scaling of the SVG when it is imported into one's editor.       | The document should be set to 72 DPI. We'd like everything to import at the same scale.                                                                                          |
| Relative Coordinates  | **Enabled**             | Changes how coordinates are stored in the SVG.                                                                           | Relative coordinates are said to help preserve the "editability" of the SVG.                                                                                                     |
| Include Bleed         | **Disabled**            |                                                                                                                          | Not relevant.                                                                                                                                                                    |
| Export Text as Curves | **Enabled**             | Bakes the text as a curve.                                                                                               | Unless you're an end-user, leave this on to maximize compatibility and reduce dependence on external fonts.                                                                      |
| Longer Text Spans     | **Enabled**             | Changes how coordinates for text are persisted.                                                                          | If the SVG does have text, leaving this enabled will result in a cleaner file structure.                                                                                         |
| Hex Colors            | **Enabled**             |                                                                                                                          | Reduces file size without a significant compromise on readability.                                                                                                               |
| Flatten Transforms    | **Enabled**             | Whether or not to `bake` the position of stuff that moved around during editing.                                         | Enable this to maximize compatibility.                                                                                                                                           |
| Tile Patterns         | **Disabled**            |                                                                                                                          | Leave this disabled to maximize compatibility.                                                                                                                                   |
| Set viewBox           | **Disabled**            | Controls what part of the SVG to show on screen.                                                                         | This setting may need to be revisited later to handle responsive viewports and/or sprites.                                                                                       |

## Visual Style

<!--
// Deliberately hidden until resolved
- **Line weight:** 2px for primary outlines, 1px for inner details.
- **Stroke color:** #333333 (unless otherwise noted for specific asset types).
- **Fill colors:** Use the official palette (see next section).
- **Transparency:** Use only if necessary for realism or clarity.
- **No drop shadows or effects** that break grid alignment.
-->

**Shadows:**
- No drop shadows or effects that break grid alignment
- A tile with a simulated shadow (done as a shape) cast onto itself is acceptable

## Color Palette

<!--
- Use the official Kerb Kit color palette (see `palette.svg` or below):
		- Pavement: #dddddd
		- Kerb: #aaaaaa
		- Road: #555555
		- Markings: #ffffff
		- Tactile paving: #ffcc00
		- [Expand as needed…]
-->
- **Map Features:** Use color and contrast to differentiate these features from the environment and from other map features.
- **Environmental Features:** Use muted, neutral colors.

## Tile Sizes

A tile of any reasonable size can be proposed, especially if it makes using the tile more practical.

Examples:
- **1x1:** The most basic tile size
- **2x1:** Useful when the width of a 1x1 tile is insufficient to capture a wide sidewalk, for example
- **6x4:** When placed directly adjacent to a six-tile-long curb section, this can be used to represent a narrow road or single lane of traffic (or a full street, if we're willing to compress proportions)

<!--

## Annotation & Labels

- **Annotations:**
		- Use arrows, bubbles, and boxes for explanatory overlays.
		- Place annotation elements on their own group/layer.
- **Text:**
		- Font: Arial, 12pt, black.
		- Keep text horizontal (not skewed), and avoid perspective text unless necessary for clarity.
		- Label according to OSM tagging where possible, e.g., `kerb=lowered`.

## Asset Organization

- **Place assets in the correct themed folder** (see `library/README.md`).
- **Templates:** Prebuilt scenes or composites should be multiples of the base cube and clearly labeled (e.g., `scene-crossing-2x3.svg`).

## Review Checklist

- [ ] Asset is aligned to the isometric 1x1x1m grid (or a clear multiple/fraction).
- [ ] SVG is clean, optimized, and uses correct palette.
- [ ] Line weight and style match the standards.
- [ ] File is named and placed correctly.
- [ ] Annotations and labels (if any) are clear and consistent.

## Tools & Resources

- [SVGOMG](https://jakearchibald.github.io/svgomg/) or [SVGO](https://github.com/svg/svgo) for optimization
- [Google Drive source files](https://drive.google.com/drive/folders/...) for editable Affinity Designer/other originals
- [Sample SVG grid/template](assets/templates/isometric-grid.svg) for new assets
-->

## Inspiration

- Adapted from [Streetmix.net](https://github.com/streetmix/streetmix), with our own isometric and modular grid approach.

## Questions?

Open an [issue](https://github.com/thompsondt/osm-kerb-kit/issues) or join the [discussion](/discussions/) if you need clarification or want to propose changes!
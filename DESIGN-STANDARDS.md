# Kerb Kit Design Standards

## Why Standards Matter

Consistent, modular assets help everyone build diagrams and scenes quickly—no matter where or how they use Kerb Kit. This guide explains how to design new illustrations and assets so they harmonize with the kit and each other.

## Isometric Perspective & Baseline Grid

- **All Kerb Kit assets use an isometric projection** (see: [wiki](https://en.wikipedia.org/wiki/Isometric_projection)), giving a sense of depth and spatial relationships.
- **Baseline grid:** Assets are aligned to a 1x1x1 meter cube (isometric). 
    - This cube is your primary building block for most features (e.g., a curb, slab, or paving stone).
    - To create smaller details, subdivide the cube into equal parts (e.g., 0.5m, 0.25m).
    - For larger features (e.g., intersections), use multiples of the cube (2x1, 3x1, etc.).
- **Snap everything to the grid:** This ensures tiles and assets will align seamlessly when assembled.

<!-- 
//todo https://github.com/thompsondt/osm-kerb-kit/issues/25
### Visual Reference

> _[Insert or link a sample SVG or PNG showing the isometric grid and a few assets at different scales]_  
-->

<!-- 
// Deliberately hidden until resolved
## File Format & Export Settings

- **Create and submit assets as plain SVG files.**
    - Remove editor metadata and unnecessary groups.
    - Optimize using tools like [SVGOMG](https://jakearchibald.github.io/svgomg/) or [SVGO](https://github.com/svg/svgo).
- **Name files descriptively and in kebab-case**, e.g., `kerb-lowered.svg`, `intersection-2x2.svg`.

## Visual Style

- **Line weight:** 2px for primary outlines, 1px for inner details.
- **Stroke color:** #333333 (unless otherwise noted for specific asset types).
- **Fill colors:** Use the official palette (see next section).
- **No embedded raster images**—vector only.
- **Transparency:** Use only if necessary for realism or clarity.
- **No drop shadows or effects** that break grid alignment.

## Color Palette

- Use the official Kerb Kit color palette (see `palette.svg` or below):
    - Pavement: #dddddd
    - Kerb: #aaaaaa
    - Road: #555555
    - Markings: #ffffff
    - Tactile paving: #ffcc00
    - [Expand as needed…]

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

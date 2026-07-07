---
name: "drawio"
description: "Generates native draw.io diagrams and optional PNG/SVG/PDF exports. Invoke when user asks to create or export diagrams, flowcharts, ER/class/sequence/architecture diagrams, wireframes, or .drawio files."
---

# Draw.io Diagram Skill

Generate draw.io diagrams as native `.drawio` files. Optionally export to PNG, SVG, or PDF with the diagram XML embedded so the exported file remains editable in draw.io.

## When To Use

Use this skill when the user asks to:

- Create or generate a diagram
- Draw a flowchart, architecture diagram, ER diagram, sequence diagram, class diagram, network diagram, wireframe, mockup, or UI sketch
- Work with `draw.io`, `drawio`, `drawoi`, or `.drawio` files
- Export a diagram to PNG, SVG, or PDF

## Workflow

1. Generate draw.io XML in `mxGraphModel` format for the requested diagram.
2. Write the XML to a `.drawio` file in the current working directory.
3. If `npx @drawio/postprocess` is available, run it on the `.drawio` file to improve edge routing. Skip silently if unavailable.
4. If the user requested `png`, `svg`, or `pdf`, locate the draw.io desktop CLI and export with embedded XML.
5. After a successful export, delete the intermediate `.drawio` file because the exported file already contains the diagram XML.
6. Open the final result if possible; otherwise report the absolute file path.

## Output Formats

If the user does not specify a format, create a `.drawio` file and open it in draw.io.

Examples:

- `draw a login flowchart` -> `login-flow.drawio`
- `png ER diagram for ecommerce` -> `ecommerce-er.drawio.png`
- `svg sequence diagram for auth flow` -> `auth-sequence.drawio.svg`
- `pdf architecture overview` -> `architecture-overview.drawio.pdf`

Supported export formats:

| Format | Notes |
|--------|-------|
| `png` | Embedded XML, viewable everywhere, still editable in draw.io |
| `svg` | Embedded XML, scalable, still editable in draw.io |
| `pdf` | Embedded XML, printable, still editable in draw.io |
| `jpg` | No embedded XML support |

## draw.io CLI

Try `where drawio` on Windows before falling back to common install paths.

Common Windows path:

```powershell
"C:\Program Files\draw.io\draw.io.exe"
```

Export command:

```powershell
drawio -x -f <format> -e -b 10 -o <output> <input.drawio>
```

Key flags:

- `-x` / `--export`: export mode
- `-f` / `--format`: output format
- `-e` / `--embed-diagram`: embed diagram XML in PNG, SVG, or PDF
- `-o` / `--output`: output file path
- `-b` / `--border`: border width

## File Naming

- Use descriptive lowercase filenames with hyphens
- Use double extensions for exports: `.drawio.png`, `.drawio.svg`, `.drawio.pdf`
- Delete the temporary `.drawio` file only after a successful export

## XML Structure

A `.drawio` file is native `mxGraphModel` XML. Always generate XML directly.

Basic structure:

```xml
<mxGraphModel adaptiveColors="auto">
  <root>
    <mxCell id="0"/>
    <mxCell id="1" parent="0"/>
  </root>
</mxGraphModel>
```

Rules:

- Cell `0` is the root layer
- Cell `1` is the default parent layer
- Diagram elements usually use `parent="1"`
- Every edge must include a child `<mxGeometry relative="1" as="geometry" />`

## XML Reference

For the shared XML reference, fetch and follow:

`https://raw.githubusercontent.com/jgraph/drawio-mcp/main/shared/xml-reference.md`

## Troubleshooting

- If the draw.io CLI is not found, keep the `.drawio` file and tell the user they can open it directly or install draw.io Desktop for export support.
- If export output is empty or corrupt, validate XML well-formedness.
- If the diagram opens blank, ensure root cells `0` and `1` exist.
- If the open command fails, print the absolute file path.

## Critical XML Rules

- Never include XML comments like `<!-- -->`
- Escape special characters in attributes: `&amp;`, `&lt;`, `&gt;`, `&quot;`
- Always use unique `id` values for each `mxCell`

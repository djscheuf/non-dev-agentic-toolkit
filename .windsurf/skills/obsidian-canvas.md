---
description: Comprehensive guide for working with Obsidian Canvas files (JSON Canvas format)
tags: [obsidian, canvas, json, visualization, mapping]
---

# Obsidian Canvas Skill

This skill provides comprehensive knowledge for creating, reading, and manipulating Obsidian Canvas files using the JSON Canvas format (`.canvas` extension).

## JSON Canvas Format Overview

Canvas files are JSON documents with two main arrays:
- `nodes`: Objects on the canvas (text, files, links, groups)
- `edges`: Connections between nodes

### File Structure
```json
{
  "nodes": [],
  "edges": []
}
```

## Node Types and Properties

### Generic Node Properties (All Types)
Every node must have:
- `id` (string): Unique identifier for the node
- `type` (string): Node type - `"text"`, `"file"`, `"link"`, or `"group"`
- `x` (integer): X position in pixels
- `y` (integer): Y position in pixels
- `width` (integer): Width in pixels
- `height` (integer): Height in pixels
- `color` (optional, string): Color code (see Color section)

### Text Nodes
Store markdown-formatted text content.

**Additional properties:**
- `text` (string): Plain text with Markdown syntax

**Example:**
```json
{
  "id": "node-1",
  "type": "text",
  "x": 100,
  "y": 200,
  "width": 300,
  "height": 150,
  "text": "# Heading\n\nSome **markdown** content",
  "color": "1"
}
```

### File Nodes
Reference other files or attachments (images, videos, etc.).

**Additional properties:**
- `file` (string): Path to the file within the vault
- `subpath` (optional, string): Subpath linking to heading/block (starts with `#`)

**Example:**
```json
{
  "id": "node-2",
  "type": "file",
  "x": 500,
  "y": 200,
  "width": 400,
  "height": 300,
  "file": "Notes/MyNote.md",
  "subpath": "#heading-name"
}
```

### Link Nodes
Reference external URLs.

**Additional properties:**
- `url` (string): The URL to link to

**Example:**
```json
{
  "id": "node-3",
  "type": "link",
  "x": 1000,
  "y": 200,
  "width": 350,
  "height": 200,
  "url": "https://example.com"
}
```

### Group Nodes
Visual containers for organizing other nodes.

**Additional properties:**
- `label` (optional, string): Text label for the group
- `background` (optional, string): Path to background image
- `backgroundStyle` (optional, string): Rendering style - `"cover"`, `"ratio"`, or `"repeat"`

**Example:**
```json
{
  "id": "group-1",
  "type": "group",
  "x": 0,
  "y": 0,
  "width": 1200,
  "height": 800,
  "label": "Genesis Phase",
  "color": "2"
}
```

## Edges (Connections)

Edges connect nodes with directional lines.

**Properties:**
- `id` (string): Unique identifier for the edge
- `fromNode` (string): Node ID where connection starts
- `fromSide` (optional, string): Side where edge starts - `"top"`, `"right"`, `"bottom"`, `"left"`
- `fromEnd` (optional, string): Endpoint shape at start - `"none"` or `"arrow"` (default: `"none"`)
- `toNode` (string): Node ID where connection ends
- `toSide` (optional, string): Side where edge ends - `"top"`, `"right"`, `"bottom"`, `"left"`
- `toEnd` (optional, string): Endpoint shape at end - `"none"` or `"arrow"` (default: `"arrow"`)
- `color` (optional, string): Line color (see Color section)
- `label` (optional, string): Text label for the edge

**Example:**
```json
{
  "id": "edge-1",
  "fromNode": "node-1",
  "fromSide": "bottom",
  "fromEnd": "none",
  "toNode": "node-2",
  "toSide": "top",
  "toEnd": "arrow",
  "label": "depends on"
}
```

## Color System

Colors can be specified as:
1. **Hex format**: `"#FF0000"` for red
2. **Preset numbers**: `"1"` through `"6"`

**Preset color mappings:**
- `"1"`: Red
- `"2"`: Orange
- `"3"`: Yellow
- `"4"`: Green
- `"5"`: Cyan
- `"6"`: Purple

Note: Specific RGB values for presets are application-defined.

## Z-Index and Layering

Nodes are rendered in array order:
- **First node** in array = bottom layer
- **Last node** in array = top layer

To change layering, reorder nodes in the array.

## Common Operations

### Creating a New Canvas

```json
{
  "nodes": [],
  "edges": []
}
```

### Adding a Text Node

1. Generate unique ID (e.g., timestamp-based or UUID)
2. Determine position (x, y) and size (width, height)
3. Add to `nodes` array

### Creating Value Chains

For dependency chains:
1. Create nodes for each component
2. Position vertically by visibility (high visibility = low y value)
3. Position horizontally by evolution stage
4. Create edges from dependent to dependency
5. Use `fromEnd: "none"` and `toEnd: "arrow"` for directional flow

### Creating Zone Groups

For visual regions (e.g., evolution stages):
1. Create group nodes as background layers
2. Position at start of nodes array (bottom layer)
3. Size to encompass the region
4. Use labels to identify zones
5. Use different colors to distinguish zones

## Best Practices

### Positioning Strategy
- **Grid alignment**: Use multiples of 50 or 100 for cleaner layouts
- **Spacing**: Leave 50-100px between nodes for readability
- **Zones**: Create large group nodes first, then position content nodes within them

### ID Generation
- Use descriptive prefixes: `persona-`, `need-`, `component-`, `edge-`
- Include timestamps or counters for uniqueness
- Keep IDs stable across updates for edge references

### Node Sizing
- **Text nodes**: Start with 250-400px width, 100-200px height
- **Group nodes**: Size to encompass all contained nodes plus padding
- **Adjust dynamically**: Based on content length and canvas layout

### Color Usage
- **Consistent meaning**: Use same colors for same types (e.g., all personas = red)
- **Zone distinction**: Different color for each evolution stage group
- **Emphasis**: Use color sparingly to highlight important nodes

### Edge Management
- **Explicit sides**: Specify `fromSide` and `toSide` for cleaner routing
- **Labels**: Add labels to clarify relationship types
- **Directionality**: Use arrows to show dependency direction (arrow points to dependency)

## Wardley Mapping Specific Patterns

### Canvas Layout for Wardley Maps

**Coordinate system:**
- **X-axis (Evolution)**: 0 = Genesis, increasing right to Commodity
- **Y-axis (Visibility)**: 0 = Low visibility, increasing down to High visibility (inverted from typical Wardley maps)

**Recommended dimensions:**
- Canvas width: 2400px (600px per evolution stage)
- Canvas height: 1600px
- Zone groups: 600px wide × 1600px tall

### Zone Group Setup

Create 4 group nodes for evolution stages:

```json
{
  "id": "zone-genesis",
  "type": "group",
  "x": 0,
  "y": 0,
  "width": 600,
  "height": 1600,
  "label": "Genesis",
  "color": "1"
}
```

Repeat for Custom (x: 600), Product (x: 1200), Commodity (x: 1800).

### Component Node Positioning

**Visibility (Y-axis):**
- User needs: y = 100-300
- First-line capabilities: y = 400-700
- Backend capabilities: y = 800-1200
- Infrastructure: y = 1300-1500

**Evolution (X-axis):**
- Genesis: x = 50-550
- Custom: x = 650-1150
- Product: x = 1250-1750
- Commodity: x = 1850-2350

### Persona Nodes

Place above the map (y = -200 to -100) as text nodes with rich content.

### Strategic Summary Node

Place to the right of the map (x = 2500+) as a large text node.

### Parking Lot Node

Place in top-right corner (x = 2500, y = 0) for "deep dive later" items.

## File Operations

### Reading a Canvas

1. Read file as JSON
2. Parse `nodes` and `edges` arrays
3. Build lookup maps by ID for efficient access

### Updating a Canvas

1. Read existing canvas
2. Modify nodes/edges arrays
3. Maintain ID references for edges
4. Write back as formatted JSON

### Incremental Updates

For progressive workflows:
1. Load existing canvas
2. Add new nodes to end of array (top layer)
3. Add new edges referencing node IDs
4. Save updated canvas
5. Obsidian will auto-reload the canvas view

## Error Prevention

### Common Issues

1. **Duplicate IDs**: Always check for ID uniqueness before adding nodes
2. **Broken edge references**: Verify `fromNode` and `toNode` IDs exist
3. **Invalid JSON**: Validate JSON structure before writing
4. **Missing required properties**: Ensure all required fields are present
5. **Type mismatches**: Use correct types (integers for positions, strings for IDs)

### Validation Checklist

Before writing canvas file:
- [ ] All nodes have unique IDs
- [ ] All nodes have required properties (id, type, x, y, width, height)
- [ ] All edge references point to existing node IDs
- [ ] JSON is valid and properly formatted
- [ ] Colors use valid values (hex or preset numbers)
- [ ] Positions are non-negative integers

## Integration with Workflows

### Progressive Visualization Pattern

For workflows that build canvases incrementally:

1. **Initialize**: Create canvas with zone groups and static elements
2. **Add incrementally**: After each workflow step, add relevant nodes
3. **Connect**: Add edges as relationships are identified
4. **Update**: Modify existing nodes as information is refined
5. **Finalize**: Add summary and strategic analysis nodes

### State Management

Store canvas path in workflow state to enable:
- Resuming interrupted sessions
- Updating existing canvases
- Creating multiple related canvases

### User Feedback

After each canvas update:
- Inform user which nodes were added
- Describe what's now visible on the canvas
- Prompt user to review canvas in Obsidian

## Example: Creating a Simple Wardley Map Canvas

```json
{
  "nodes": [
    {
      "id": "zone-genesis",
      "type": "group",
      "x": 0,
      "y": 0,
      "width": 600,
      "height": 1600,
      "label": "Genesis",
      "color": "1"
    },
    {
      "id": "zone-custom",
      "type": "group",
      "x": 600,
      "y": 0,
      "width": 600,
      "height": 1600,
      "label": "Custom",
      "color": "2"
    },
    {
      "id": "zone-product",
      "type": "group",
      "x": 1200,
      "y": 0,
      "width": 600,
      "height": 1600,
      "label": "Product",
      "color": "3"
    },
    {
      "id": "zone-commodity",
      "type": "group",
      "x": 1800,
      "y": 0,
      "width": 600,
      "height": 1600,
      "label": "Commodity",
      "color": "4"
    },
    {
      "id": "persona-1",
      "type": "text",
      "x": 100,
      "y": -150,
      "width": 400,
      "height": 100,
      "text": "## Product Manager\n\n**Values:** Deliver valuable software quickly\n**Incentives:** Team velocity, customer satisfaction",
      "color": "6"
    },
    {
      "id": "need-1",
      "type": "text",
      "x": 300,
      "y": 200,
      "width": 300,
      "height": 80,
      "text": "**Need:** Deliver valuable software",
      "color": "5"
    },
    {
      "id": "component-1",
      "type": "text",
      "x": 1250,
      "y": 500,
      "width": 200,
      "height": 60,
      "text": "CI/CD Pipeline"
    },
    {
      "id": "component-2",
      "type": "text",
      "x": 1850,
      "y": 900,
      "width": 200,
      "height": 60,
      "text": "Cloud Hosting"
    }
  ],
  "edges": [
    {
      "id": "edge-1",
      "fromNode": "need-1",
      "fromSide": "bottom",
      "toNode": "component-1",
      "toSide": "top",
      "toEnd": "arrow"
    },
    {
      "id": "edge-2",
      "fromNode": "component-1",
      "fromSide": "bottom",
      "toNode": "component-2",
      "toSide": "top",
      "toEnd": "arrow"
    }
  ]
}
```

## Resources

- **Official Spec**: https://jsoncanvas.org/spec/1.0
- **GitHub**: https://github.com/obsidianmd/jsoncanvas
- **Obsidian Help**: https://help.obsidian.md/plugins/canvas

## Supporting Files

This skill provides the foundation for:
- Wardley Mapping workflows
- Visual brainstorming tools
- System architecture diagrams
- Knowledge graph visualizations
- Any spatial organization of information

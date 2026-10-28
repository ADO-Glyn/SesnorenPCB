# KiCAD & Konnect Operating Rules

## The One Rule
**KiCAD source files (*.kicad_sch, *.kicad_pcb, *.kicad_pro, *.kicad_sym, *.kicad_mod) are serialized object graphs with UUIDs and cross-references. Never edit them directly with raw text manipulation tools.**
All modifications should go through Konnect MCP tools.

## Using Konnect MCP Tools
- Konnect uses an on-demand toolset loader:
  - `list_toolboxes` — View available toolsets
  - `load_toolset` — Activate a toolset (e.g., `sch_components`, `sch_wiring`, `sch_analysis`, `pcb_board`, `pcb_components`, `pcb_routing`, `verification`, `pcb_export`, etc.)
  - `get_active_toolsets` — Check currently loaded toolsets
- **KiCad 10 IPC API**: Live PCB layout requires KiCad running with the project board open and "Enable KiCad API" checked in Preferences -> Plugins.
- **Schematics**: Schematic operations use Konnect's native validated S-expression engine and work directly with the schematic files with atomic writes.

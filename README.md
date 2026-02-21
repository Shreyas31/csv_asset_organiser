# CSVAssetOrganiser: Unreal Engine Plugin for VFX Asset Management

CSVAssetOrganiser is a pipeline tool developed to simplify the integration of external assets into Unreal Engine (UE) for small teams and independent filmmakers. By utilizing standardized CSV spreadsheets, the plugin automates complex organizational and importing tasks, reducing the steep learning curve associated with UE's manual asset management.

## Features

**Automated Batch Importing**: Streamlines the process of bringing in 3D models (characters, props, environment), cameras, and textures by reading absolute file paths directly from a CSV.
**Production-Based Organization**: Automatically generates a structured project hierarchy (e.g., `Export/Shot_Name/Asset_Type/`) to keep assets organized by their specific role in a sequence.
**Sequencer Integration**: Uses shot data (ID, Shot Name, and Frame Data) to facilitate the creation of cinematic timelines, ensuring assets are associated with the correct frame ranges and shot numbers.
**Hybrid Scripting System**: Leverages Unreal Engine Blueprints for the front-end Editor Utility Widgets and logic, while using the **Python API** to handle robust file system operations and automation.
**Enhanced Accessibility**: Specifically designed as a simpler alternative to industry-standard asset management software, making it ideal for virtual production and real-time filmmaking projects by independent filmmakers.

## Project Structure

The plugin is divided into two primary modules to handle the production lifecycle:

**AssetImport**: Contains the `EUW_AssetImportOrganiser` widget and `DT_Import` data table for ingesting external content.
**AssetExport**: Manages outgoing data through the `EUW_AssetExportOrganiser` and `DT_Export` table to maintain consistency across the pipeline.

## Setup & Requirements

### Spreadsheet Format

For the plugin to correctly interpret your data, input CSVs (such as `AssetImportTest.csv`) must follow this header structure:

`ID`: Unique identifier for the row.
`ShotName`: The specific shot identifier (e.g., `Shot_001`).
`AssetName`: Desired name for the actor in the engine.
`AssetPath`: Absolute path to the source file.
`AssetType`: Category for folder sorting (Character, Prop, Camera, Texture, Environment).
`Frames`, `Frame In`, `Frame Out`: Timing data for Sequencer integration.

### Dependencies

**Unreal Engine**: The primary host application.
**Python Editor Script Plugin**: Must be enabled in Unreal Engine to allow the background automation scripts to run.

## Installation

1. Place the `CSVAssetOrganiser` folder into your Unreal Engine project's `Plugins/` directory and restart Unreal Engine.
2. Enable the **CSV Asset Organiser** and **Python Editor Script** plugins via the **Edit > Plugins** menu.
3. Launch the `EUW_AssetImportOrganiser` from the Content Browser to begin importing assets based on your production spreadsheet.

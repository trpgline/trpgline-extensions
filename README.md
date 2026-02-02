# TRPG Line Character Extensions

This repository stores character extensions for various Tabletop Role-Playing Game (TRPG) systems.

## Overview

Character extensions provide additional functionality, traits, abilities, or customizations for characters in different TRPG systems. This repository serves as a central collection point for these extensions across multiple game systems.

## Supported Systems

Each TRPG system has its own directory containing character extensions specific to that system:

- **dnd5e** - Dungeons & Dragons 5th Edition
- **pathfinder2e** - Pathfinder 2nd Edition
- **call-of-cthulhu** - Call of Cthulhu
- **shadowrun** - Shadowrun
- **world-of-darkness** - World of Darkness
- **fate** - Fate Core/Accelerated
- **savage-worlds** - Savage Worlds

## Repository Structure

```
trpgline-extensions/
├── README.md
├── CONTRIBUTING.md
├── systems/
│   ├── dnd5e/
│   │   ├── README.md
│   │   └── extensions/
│   │       └── example-extension.json
│   ├── pathfinder2e/
│   │   ├── README.md
│   │   └── extensions/
│   └── ...
└── schema/
    └── extension-schema.json
```

## Character Extension Format

Each character extension is stored as a JSON file with the following structure:

```json
{
  "name": "Extension Name",
  "version": "1.0.0",
  "system": "dnd5e",
  "description": "Description of what this extension does",
  "author": "Author Name",
  "type": "trait|ability|feature|background|class",
  "data": {
    // System-specific extension data
  }
}
```

## Contributing

To contribute a new character extension:

1. Choose the appropriate system directory
2. Create a new JSON file following the extension format
3. Validate your extension against the schema
4. Submit a pull request

For detailed guidelines, see [CONTRIBUTING.md](CONTRIBUTING.md).

## License

See individual extensions for their respective licenses.
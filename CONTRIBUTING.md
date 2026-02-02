# Contributing to TRPG Line Character Extensions

Thank you for your interest in contributing to the TRPG Line Character Extensions repository!

## How to Contribute

### Adding a New Character Extension

1. **Choose the appropriate system directory**
   - Navigate to the `systems/` directory
   - Select the folder for your TRPG system (e.g., `dnd5e`, `pathfinder2e`)
   - If the system doesn't exist, create a new directory with a README

2. **Create your extension file**
   - Create a new JSON file in the `extensions/` subdirectory
   - Use a descriptive filename (e.g., `arcane-trickster.json`, `combat-medic.json`)
   - Follow the extension schema format

3. **Validate your extension**
   - Ensure your JSON is valid
   - Check that all required fields are present
   - Verify the data structure matches the schema

4. **Submit a pull request**
   - Provide a clear description of the extension
   - Include any relevant game rules or sources
   - Note any dependencies or prerequisites

### Extension File Format

All character extensions must follow this structure:

```json
{
  "name": "Extension Name",
  "version": "1.0.0",
  "system": "system-name",
  "description": "Clear description of what this extension provides",
  "author": "Your Name or Username",
  "type": "trait|ability|feature|background|class|race|skill|equipment",
  "tags": ["optional", "categorization", "tags"],
  "data": {
    // System-specific extension data goes here
    // Structure varies by TRPG system
  }
}
```

### Required Fields

- `name`: The name of the extension
- `version`: Semantic version number (e.g., "1.0.0")
- `system`: The TRPG system this extension is for
- `description`: A clear description of the extension
- `author`: Your name or username
- `type`: The category of extension
- `data`: System-specific extension data

### Optional Fields

- `tags`: Array of tags for categorization
- `license`: License information (defaults to repository license)
- `source`: Source material or rulebook reference
- `prerequisites`: Required character level, stats, or other extensions

### Guidelines

1. **Be Specific**: Clearly describe what the extension does
2. **Follow System Rules**: Ensure extensions align with the target system's mechanics
3. **Avoid Duplicates**: Check if a similar extension already exists
4. **Test Your JSON**: Validate JSON syntax before submitting
5. **Respect Licenses**: Only include content you have rights to share

### Adding a New TRPG System

To add support for a new TRPG system:

1. Create a new directory under `systems/` with the system name (use kebab-case)
2. Add a `README.md` explaining the system and extension format
3. Create an `extensions/` subdirectory
4. Add at least one example extension

### Code of Conduct

- Be respectful and constructive
- Give credit to original creators
- Respect intellectual property rights
- Help others learn and improve

## Questions?

If you have questions about contributing, please open an issue for discussion.

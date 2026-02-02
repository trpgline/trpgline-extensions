# D&D 5e Character Extensions

This directory contains character extensions for Dungeons & Dragons 5th Edition.

## Extension Types

- **class**: Custom character classes or class variants
- **race**: Custom races or race variants
- **background**: Character backgrounds
- **feat**: Custom feats
- **trait**: Racial traits or character traits
- **ability**: Special abilities
- **spell**: Custom spells
- **equipment**: Custom equipment or magical items

## Extension Format

D&D 5e extensions should include relevant game mechanics in the `data` field:

```json
{
  "name": "Example Feature",
  "version": "1.0.0",
  "system": "dnd5e",
  "description": "An example character feature",
  "author": "Author Name",
  "type": "feat",
  "data": {
    "requirements": {
      "level": 1,
      "attributes": {
        "strength": 13
      }
    },
    "benefits": {
      "description": "Description of what this feat provides",
      "mechanics": []
    }
  }
}
```

## Examples

See the `extensions/` directory for example character extensions.

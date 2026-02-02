# Pathfinder 2e Character Extensions

This directory contains character extensions for Pathfinder 2nd Edition.

## Extension Types

- **class**: Custom character classes or archetypes
- **ancestry**: Custom ancestries or heritage options
- **background**: Character backgrounds
- **feat**: Ancestry, class, or general feats
- **trait**: Character traits
- **ability**: Special abilities
- **spell**: Custom spells
- **equipment**: Custom equipment or magical items

## Extension Format

Pathfinder 2e extensions should follow the system's action economy and trait system:

```json
{
  "name": "Example Feat",
  "version": "1.0.0",
  "system": "pathfinder2e",
  "description": "An example feat",
  "author": "Author Name",
  "type": "feat",
  "data": {
    "level": 1,
    "traits": ["general"],
    "prerequisites": [],
    "actions": "1",
    "effect": "Description of the feat's effect"
  }
}
```

## Examples

See the `extensions/` directory for example character extensions.

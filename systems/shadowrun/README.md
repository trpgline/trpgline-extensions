# Shadowrun Character Extensions

This directory contains character extensions for Shadowrun.

## Extension Types

- **trait**: Character qualities (positive/negative)
- **skill**: Custom skills or skill specializations
- **ability**: Special abilities
- **equipment**: Custom gear, cyberware, or bioware
- **spell**: Custom spells or adept powers
- **background**: Character background elements

## Extension Format

Shadowrun extensions should include karma costs and game mechanics:

```json
{
  "name": "Example Quality",
  "version": "1.0.0",
  "system": "shadowrun",
  "description": "An example quality",
  "author": "Author Name",
  "type": "trait",
  "data": {
    "karma_cost": 5,
    "type": "positive",
    "effect": "Description of the quality's effect"
  }
}
```

## Examples

See the `extensions/` directory for example character extensions.

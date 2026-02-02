# World of Darkness Character Extensions

This directory contains character extensions for World of Darkness games.

## Extension Types

- **trait**: Character merits, flaws, or derangements
- **ability**: Disciplines, gifts, or special abilities
- **background**: Character backgrounds
- **equipment**: Custom equipment or fetishes

## Extension Format

World of Darkness extensions should include dot ratings and supernatural mechanics:

```json
{
  "name": "Example Merit",
  "version": "1.0.0",
  "system": "world-of-darkness",
  "description": "An example merit",
  "author": "Author Name",
  "type": "trait",
  "data": {
    "cost": 2,
    "type": "merit",
    "effect": "Description of the merit's effect"
  }
}
```

## Examples

See the `extensions/` directory for example character extensions.

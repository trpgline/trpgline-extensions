# Fate Character Extensions

This directory contains character extensions for Fate Core and Fate Accelerated.

## Extension Types

- **trait**: Aspects, stunts, or extras
- **skill**: Custom skills
- **ability**: Special abilities or powers

## Extension Format

Fate extensions should use the Fate Point economy and aspect-based mechanics:

```json
{
  "name": "Example Stunt",
  "version": "1.0.0",
  "system": "fate",
  "description": "An example stunt",
  "author": "Author Name",
  "type": "ability",
  "data": {
    "cost": 1,
    "type": "stunt",
    "effect": "Description of the stunt's effect",
    "associated_skill": "Fight"
  }
}
```

## Examples

See the `extensions/` directory for example character extensions.

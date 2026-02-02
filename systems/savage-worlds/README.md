# Savage Worlds Character Extensions

This directory contains character extensions for Savage Worlds.

## Extension Types

- **trait**: Edges and hindrances
- **ability**: Special abilities or powers
- **skill**: Custom skills
- **equipment**: Custom gear or weapons

## Extension Format

Savage Worlds extensions should include rank requirements and game mechanics:

```json
{
  "name": "Example Edge",
  "version": "1.0.0",
  "system": "savage-worlds",
  "description": "An example edge",
  "author": "Author Name",
  "type": "trait",
  "data": {
    "type": "combat",
    "requirements": {
      "rank": "Novice",
      "attributes": {},
      "skills": {}
    },
    "effect": "Description of the edge's effect"
  }
}
```

## Examples

See the `extensions/` directory for example character extensions.

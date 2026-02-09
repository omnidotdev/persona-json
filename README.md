<div align="center">

# persona.json Schema

JSON Schema specification for portable non-human identity

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE.md)

</div>

## Overview

persona.json defines non-human identities -- AI assistants, brands, bots, mascots, and any entity that presents a public-facing identity.

## Structure

```
persona.schema.json          # Root schema
slices/
├── identity.schema.json     # Core identity (required)
├── voice.schema.json        # Voice/audio settings
├── personality.schema.json  # Behavior and communication
├── branding.schema.json     # Visual identity
└── capabilities.schema.json # Permissions and tools
```

## Slices

| Slice | Required | Description |
|-------|----------|-------------|
| identity | Yes | Core identity: id, name, tagline, icon |
| voice | No | Wake words, TTS/STT configuration |
| personality | No | System prompt, tone, expertise |
| branding | No | Colors, description, assets |
| capabilities | No | Tool policies, channel permissions |

## Usage

```json
{
  "$schema": "https://persona.omni.dev/persona.schema.json",
  "identity": {
    "id": "orin",
    "name": "Orin",
    "tagline": "Your friendly otter guide",
    "icon": "🦦"
  }
}
```

## Validation

```bash
npx ajv validate -s persona.schema.json -d examples/orin.json
```

## License

The code in this repository is licensed under MIT, &copy; [Omni LLC](https://omni.dev). See [LICENSE.md](LICENSE.md) for more information.

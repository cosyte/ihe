<a href="https://cosyte.com">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://cosyte.com/tile/cosyte-lockup-tile-on-dark-1200x300.png">
    <img alt="The Cosyte logo on its own white ground: the icon beside the word Cosyte." src="https://cosyte.com/tile/cosyte-lockup-tile-on-light-1200x300.png">
  </picture>
</a>

# @cosyte/ihe

> IHE cross-community exchange for Node.js and TypeScript: lenient on parse, spec-clean on emit.

[![npm version](https://img.shields.io/npm/v/@cosyte/ihe.svg)](https://www.npmjs.com/package/@cosyte/ihe)
[![CI](https://img.shields.io/github/actions/workflow/status/cosyte/ihe/ci.yml?branch=main&label=CI)](https://github.com/cosyte/ihe/actions/workflows/ci.yml)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://github.com/cosyte/ihe/blob/main/LICENSE)
[![Node](https://img.shields.io/badge/node-%3E%3D22-brightgreen.svg)](https://nodejs.org)

## Why this exists

Real-world IHE cross-community exchange messages depart from the specification in vendor-specific ways. `@cosyte/ihe`
reads them leniently, turning each quirk into a warning with a stable code instead of a failure,
and writes spec-clean output, so a quirk does not travel downstream on a round trip. It follows
the Cosyte parser archetype and mirrors the API of [`@cosyte/hl7`](https://github.com/cosyte/hl7).

## Status

Pre-alpha, on the 0.0.x line, and not yet published to npm. Nothing here reads or writes an IHE
message yet: this repository holds the scaffold only, and the API below is a placeholder.

What we plan to build here, in the open:

- the patient discovery messages (HL7 version 3) and the document query, retrieve and push
  messages with their document metadata, as the IHE cross-community profiles define them;
- the SAML assertion and XML signature handling those profiles require;
- the audit records they require.

This package implements message formats. It is not a gateway, it carries no network membership or
certificates, and we make no claim of certification by any exchange network or by IHE.

## Install

```bash
npm install @cosyte/ihe
```

Node 22 or later. No runtime dependencies.

## Usage

```ts
import { parseIhe } from "@cosyte/ihe";

const result = parseIhe(raw);

result.warnings; // stable, positional tolerance warnings: a quirk never throws
```

The parser is lenient by default: vendor quirks become warnings, not failures.

## Documentation

The guides and the API reference are at
[docs.cosyte.com/ihe](https://docs.cosyte.com/ihe).

## Support

Ask a question or report a bug in [GitHub issues](https://github.com/cosyte/ihe/issues). Use
synthetic data only: never paste a real message.

## Security

Report a vulnerability privately, as our
[security policy](https://github.com/cosyte/.github/blob/main/SECURITY.md) describes, never in a
public issue.

## Contributing

See [CONTRIBUTING](https://github.com/cosyte/.github/blob/main/CONTRIBUTING.md). Fixtures are
synthetic only.

## License

MIT, Cosyte LLC. See [LICENSE](https://github.com/cosyte/ihe/blob/main/LICENSE).

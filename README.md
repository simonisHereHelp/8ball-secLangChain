# SEC EDGAR Agent Kit (LangChain-focused)

SEC EDGAR Agent Kit provides a LangChain toolkit for working with SEC filings through the `sec-edgar-mcp` server.

## What changed

- Repository simplified to LangChain-only integration.
- Legacy non-LangChain integrations and framework-specific example folders were removed.
- Example scripts were flattened from `examples/langchain` into [`app/`](./app/).

## Installation

```bash
bun install
```

## Prerequisites

- [Bun](https://bun.sh/)
- `sec-edgar-mcp` server (`pip install sec-edgar-mcp`)
- An LLM provider key (for example OpenAI)

## LangChain Toolkit (TypeScript)

```ts
import { SECEdgarAgentToolkit } from './integrations/langchain/typescript';

const toolkit = new SECEdgarAgentToolkit({
  mcpServerUrl: 'sec-edgar-mcp',
  configuration: {
    actions: {
      companies: { lookupCIK: true, getInfo: true },
      filings: { search: true, getContent: true },
      financial: { getStatements: true, parseXBRL: true }
    }
  }
});
```

## Examples

Run local examples:

```bash
bun run app/basic-usage.ts
bun run app/financial-analysis.ts
```

## Directory layout

```text
app/                                # runnable LangChain examples
integrations/langchain/typescript/  # TypeScript package
integrations/langchain/python/      # Python package
```

## License

AGPL-3.0. See [LICENSE](./LICENSE).

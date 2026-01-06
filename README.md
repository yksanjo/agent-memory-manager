# Agent Memory Management Library

A TypeScript library providing hierarchical memory compression, context window prediction, memory indexing for fast recall, and multi-turn conversation replay for debugging.

## Features

- Hierarchical memory compression (summaries → embeddings → keys)
- Context window prediction & automatic truncation
- Memory indexing for fast recall (integrates with Pinecone/Weaviate)
- Multi-turn conversation replay for debugging
- TypeScript/JavaScript library with Python bindings

## Installation

```bash
npm install agent-memory-manager
```

## Usage

```typescript
import { MemoryManager } from 'agent-memory-manager';

const memoryManager = new MemoryManager({
  maxContextLength: 4096,
  compressionThreshold: 1000
});

// Store conversation history
await memoryManager.store('session-123', [
  { role: 'user', content: 'Hello' },
  { role: 'assistant', content: 'Hi there!' }
]);

// Retrieve compressed memory
const compressed = await memoryManager.getCompressed('session-123');
```

## Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

## License

MIT
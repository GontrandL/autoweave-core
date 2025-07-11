# @autoweave/core

Core orchestration module for AutoWeave - the self-weaving agent orchestrator.

## Description

This module contains the core functionality for AutoWeave, including:
- **Agent Weaver**: Natural language to agent definition conversion
- **AutoWeave Core**: Main orchestration engine with ANP and AG-UI integration
- **Configuration Intelligence**: AI-powered configuration generation
- **Utilities**: Logging, retry logic, and validation

## Installation

```bash
npm install @autoweave/core
```

## Usage

```javascript
const { AutoWeave } = require('@autoweave/core');

const autoweave = new AutoWeave({
  openaiApiKey: process.env.OPENAI_API_KEY,
  kagentNamespace: 'default'
});

// Create an agent from natural language
const agent = await autoweave.createAgent({
  description: 'Create a file processing agent'
});
```

## API

### AutoWeave

Main orchestration class for agent creation and management.

### AgentWeaver

Converts natural language descriptions to structured agent definitions.

### ConfigurationIntelligence

Generates optimal configurations with AI assistance.

## Development

```bash
# Install dependencies
npm install

# Run in development mode
npm run dev

# Run tests
npm test

# Lint code
npm run lint
```

## License

MIT
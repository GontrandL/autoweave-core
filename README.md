# @autoweave/core

Core engine module for AutoWeave - The Self-Weaving Agent Orchestrator

## Overview

This module contains the core components of AutoWeave:

- **Agent Weaver**: Converts natural language descriptions into structured agent definitions
- **Configuration Intelligence**: AI-powered configuration generation with package discovery
- **Agent Service**: Core business logic for agent management
- **Fresh Sources Service**: Multi-registry package version discovery
- **Utilities**: Logger, retry logic, and validation helpers

## Installation

```bash
npm install @autoweave/core
```

## Usage

```javascript
const { AutoWeave } = require('@autoweave/core');
const { AgentWeaver } = require('@autoweave/core/agent-weaver');
const { ConfigurationIntelligence } = require('@autoweave/core/config-intelligence');

// Initialize AutoWeave
const autoweave = new AutoWeave({
  openaiApiKey: process.env.OPENAI_API_KEY,
  kagentNamespace: 'default'
});

// Create an agent from natural language
const agent = await autoweave.createAgent({
  description: 'Create a file processing agent that monitors a directory'
});
```

## Components

### Core Engine (src/core/)
- `autoweave.js` - Main AutoWeave orchestrator class
- `agent-weaver.js` - Natural language to agent definition converter
- `config-intelligence.js` - Intelligent configuration generation

### Services (src/services/)
- `agent-service.js` - Agent lifecycle management
- `fresh-sources-service.js` - Package version discovery across registries

### Utilities (src/utils/)
- `logger.js` - Structured logging with configurable levels
- `dev-logger.js` - Development-specific logging utilities
- `retry.js` - Retry logic with exponential backoff
- `validation.js` - Input validation helpers

### Configuration (config/autoweave/)
- `config.js` - Base configuration
- `config.test.js` - Test configuration

## API Reference

### AutoWeave Class

```javascript
new AutoWeave(options)
```

Options:
- `openaiApiKey`: OpenAI API key for agent generation
- `kagentNamespace`: Kubernetes namespace for deployment
- `logLevel`: Logging level (debug, info, warn, error)

Methods:
- `createAgent(params)`: Create agent from description
- `getAgent(agentId)`: Get agent by ID
- `deleteAgent(agentId)`: Delete agent
- `listAgents()`: List all agents

### AgentWeaver Class

```javascript
new AgentWeaver(openaiApiKey, options)
```

Methods:
- `weaveAgent(description, options)`: Convert description to agent definition
- `generateAgentManifest(agentDefinition)`: Generate Kubernetes manifest

### ConfigurationIntelligence Class

```javascript
new ConfigurationIntelligence()
```

Methods:
- `generateConfiguration(intent, options)`: Generate intelligent configuration
- `discoverFreshVersions(packages)`: Discover latest package versions

## Dependencies

Core dependencies:
- `openai` - OpenAI API client for AI-powered features
- `ajv` - JSON schema validation
- `axios` - HTTP client
- `chalk` - Terminal styling
- `express` - Web framework (for API routes)
- `swagger-parser` - OpenAPI specification parsing

## Development

```bash
# Install dependencies
npm install

# Run tests
npm test

# Run linter
npm run lint

# Fix linting issues
npm run lint:fix
```

## License

MIT License - see LICENSE file for details

## Repository Structure

```
autoweave-core/
├── src/
│   ├── core/           # Core engine components
│   ├── services/       # Business logic services
│   └── utils/          # Utility functions
├── config/
│   └── autoweave/      # Configuration files
├── package.json
└── README.md
```
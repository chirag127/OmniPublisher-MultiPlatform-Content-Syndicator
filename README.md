# OmniPublish-Multi-Platform-Content-Distribution-Node-CLI-Tool

[![Build Status](https://img.shields.io/github/actions/workflow/status/chirag127/OmniPublish-Multi-Platform-Content-Distribution-Node-CLI-Tool/ci.yml?branch=main&label=Build&style=flat-square)](https://github.com/chirag127/OmniPublish-Multi-Platform-Content-Distribution-Node-CLI-Tool/actions/workflows/ci.yml)
[![Code Coverage](https://img.shields.io/codecov/c/github/chirag127/OmniPublish-Multi-Platform-Content-Distribution-Node-CLI-Tool?style=flat-square)](https://codecov.io/gh/chirag127/OmniPublish-Multi-Platform-Content-Distribution-Node-CLI-Tool)
[![Language](https://img.shields.io/github/languages/top/chirag127/OmniPublish-Multi-Platform-Content-Distribution-Node-CLI-Tool?style=flat-square)](https://github.com/chirag127/OmniPublish-Multi-Platform-Content-Distribution-Node-CLI-Tool)
[![License](https://img.shields.io/github/license/chirag127/OmniPublish-Multi-Platform-Content-Distribution-Node-CLI-Tool?style=flat-square)](https://github.com/chirag127/OmniPublish-Multi-Platform-Content-Distribution-Node-CLI-Tool/blob/main/LICENSE)
[![GitHub Stars](https://img.shields.io/github/stars/chirag127/OmniPublish-Multi-Platform-Content-Distribution-Node-CLI-Tool?style=flat-square)](https://github.com/chirag127/OmniPublish-Multi-Platform-Content-Distribution-Node-CLI-Tool/stargazers)

## Introduction

A TypeScript-powered CLI that writes Markdown once and automatically publishes to 17+ platforms, generates a static archive site, and supports scheduled and issue-driven publishing.

## Table of Contents

* [Introduction](#introduction)
* [Getting Started](#getting-started)
* [Architecture](#architecture)
* [AI Agent Directives](#ai-agent-directives)
* [Contributing](#contributing)
* [License](#license)

## Getting Started

1. Clone the repository: `git clone https://github.com/chirag127/OmniPublish-Multi-Platform-Content-Distribution-Node-CLI-Tool.git`
2. Install dependencies: `npm install`
3. Run the application: `npm start`

## Architecture

The application uses a modular architecture, with the following components:

* `src/`: Application logic
* `tests/`: Verification and validation tests
* `scripts/`: Maintenance and build scripts
* `.github/`: CI/CD and template configurations

## AI Agent Directives

For AI operations, this repository uses the Cerebras Inference API via the OpenAI SDK.

### Client Configuration

* **Base URL:** `https://api.cerebras.ai/v1`
* **API Key Variable:** `CEREBRAS_API_KEY`
* **Library:** `openai`

javascript
const { OpenAI } = require('openai');
const client = new OpenAI({
  base_url: 'https://api.cerebras.ai/v1',
  api_key: process.env.CEREBRAS_API_KEY,
});


### Model Hierarchy (Fallback Cascade)

The application uses the following model hierarchy:

* **Tier 1 (Frontier Intelligence):** `zai-glm-4.6` (357B)
* **Tier 2 (Heavy Reasoning):** `qwen-3-235b-a22b-instruct-2507` (235B)
* **Tier 3 (General Purpose):** `gpt-oss-120b` (120B)
* **Tier 4 (Balanced Workhorse):** `llama-3.3-70b` (70B)
* **Tier 5 (Fast Inference):** `qwen-3-32b` (32B)
* **Tier 6 (Ultra-Fast/Instant):** `llama3.1-8b` (8B)

## Contributing

Contributions are welcome! Please see the [Contributing Guidelines](https://github.com/chirag127/OmniPublish-Multi-Platform-Content-Distribution-Node-CLI-Tool/blob/main/CONTRIBUTING.md) for more information.

## License

This project is licensed under the [CC BY-NC 4.0](https://github.com/chirag127/OmniPublish-Multi-Platform-Content-Distribution-Node-CLI-Tool/blob/main/LICENSE) license.

Star ⭐ this repository if you find it useful!
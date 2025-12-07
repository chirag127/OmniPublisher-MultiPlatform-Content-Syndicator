# OmniPublisher-MultiPlatform-Content-Syndicator

![OmniPublisher Logo Placeholder](https://img.shields.io/badge/OmniPublisher-Syndication%20Engine-blue?style=for-the-badge&logo=rss)

[![Build Status](https://img.shields.io/github/actions/workflow/status/chirag127/OmniPublisher-MultiPlatform-Content-Syndicator/ci.yml?label=Build&style=flat-square)](https://github.com/chirag127/OmniPublisher-MultiPlatform-Content-Syndicator/actions/workflows/ci.yml)
[![Code Coverage](https://img.shields.io/codecov/c/github/chirag127/OmniPublisher-MultiPlatform-Content-Syndicator?label=Coverage&style=flat-square)](https://codecov.io/gh/chirag127/OmniPublisher-MultiPlatform-Content-Syndicator)
[![TypeScript](https://img.shields.io/badge/Language-TypeScript-3178C6?style=flat-square&logo=typescript)](https://www.typescriptlang.org/)
[![License](https://img.shields.io/badge/License-CC%20BY--NC%204.0-FF69B4?style=flat-square)](LICENSE)
[![GitHub Stars](https://img.shields.io/github/stars/chirag127/OmniPublisher-MultiPlatform-Content-Syndicator?style=flat-square)](https://github.com/chirag127/OmniPublisher-MultiPlatform-Content-Syndicator)

**Star ⭐ this Repo to track the evolution of multi-platform content automation.**

---

## 🚀 Project Overview: BLUF

**OmniPublisher** is a TypeScript-based, CI/CD-integrated engine designed to syndicate long-form content from a single Markdown source across numerous external platforms (Dev.to, Medium, Hashnode, WordPress, etc.) with built-in idempotency checks. This system centralizes content workflow, transforming the tedious task of cross-posting into a zero-touch, declarative DevOps pipeline.

## 🏗️ Architecture Diagram

mermaid
flowchart TD
    A[Source: Single Markdown File] --> B{OmniPublisher Engine (TS)};
    B -- Platform Adapters --> C(Dev.to Adapter);
    B -- Platform Adapters --> D(Medium Adapter);
    B -- Platform Adapters --> E(Hashnode Adapter);
    B -- Platform Adapters --> F(WordPress Adapter);
    B -- Platform Adapters --> G(Social/RSS Syndication);
    C & D & E & F & G --> H[Idempotency Check & Publish API Call];
    H -- Success/Failure Logs --> I(CI/CD Artifact Storage);
    subgraph CI/CD Pipeline
        J[Trigger: Git Push/Schedule] --> B;
    end


## 📋 Table of Contents

1. [🚀 Project Overview: BLUF](#-project-overview-bluf)
2. [🏗️ Architecture Diagram](#-architecture-diagram)
3. [📋 Table of Contents](#-%EF%B8%8F-table-of-contents)
4. [✨ Key Features](#-%E2%9C%A8-key-features)
5. [🤖 AI Agent Directives (APEX Standard)](#-%F0%9F%A7%99-ai-agent-directives-apex-standard)
6. [🛠️ Development Standards](#-%E2%9A%99%EF%B8%8F-development-standards)
7. [📚 Licensing](#-%F0%9F%93%9A-licensing)

## ✨ Key Features

*   **Universal Markdown Ingestion:** Parses standardized Markdown files (`.md`) as the single source of truth.
*   **Platform Abstraction Layer:** Uses adapter patterns to decouple the core logic from specific API requirements of each destination platform (e.g., Medium's specific token handling vs. Dev.to's simpler POST).
*   **Idempotent Publishing:** Prevents duplicate content creation by checking existing post IDs or canonical URLs before publication.
*   **Declarative Configuration:** Configuration via structured YAML/JSON defining platform credentials and syndication rules.
*   **DevOps Native:** Built for execution within GitHub Actions, allowing scheduled or manual triggers for mass syndication.
*   **TypeScript Reliability:** Leveraging strict typing for robust compile-time error checking across complex API interactions.

## 🤖 AI Agent Directives (APEX Standard)

<details>
<summary>Click to Expand Apex Agent Configuration & Verification</summary>

### 1. IDENTITY & PRIME DIRECTIVE
**Role:** Senior Principal Software Architect. Enforce **FAANG-level standards** and the wisdom of "Managing the Unmanageable." **Output Standard:** **EXECUTION-ONLY** results.
**Philosophy:** "Zero-Defect, High-Velocity, Future-Proof."

### 2. INPUT PROCESSING & COGNITION
*   **Semantic Correction:** STIRCTLY FORBIDDEN from executing literal typos. Must **INFER** technical intent based on project context. 
*   **Validation:** Use `linkup`/`brave` to search for **December 2025 Industry Standards** concerning content API rate limiting and security protocols. Verify *every* external API signature using `docfork`.

### 3. CONTEXT-AWARE APEX TECH STACKS (LATE 2025 STANDARDS)
*   **PRIMARY SCENARIO: WEB / APP / CLI (TypeScript)**
    *   **Stack:** This project leverages **TypeScript 6.x (Strict)**, **Vite 7** (for bundling configuration tooling if needed), and relies heavily on Node.js `fetch` for HTTP interactions.
    *   **Architecture:** Adheres strictly to **Feature-Sliced Design (FSD)** principles for modularity. Core logic is separated into `domain` (business rules), `data` (API interactions), and `ui/cli` (interface).
    *   **Linting/Formatting:** **Biome** is mandatory for formatting and linting to ensure ultra-fast, unified code style. **Vitest** must cover all adapters and core parsing logic.

### 4. CORE VERIFICATION COMMANDS (For Self-Correction)
bash
# 1. Dependency Check & Lockfile Update (uv equivalent for Node)
npm install

# 2. Ultra-Fast Linting and Formatting Check
# Biome must pass 100% before any commit/PR merge.
npm run lint:check

# 3. Unit Test Execution (Vitest)
npm run test:unit

# 4. Static Analysis of Platform Adapters (Ensuring API contracts are met)
# Future Agent Check: Verify all platform API wrappers against their latest documentation.
# node dist/scripts/verify-adapters.js --platform=medium


</details>

## 🛠️ Development Standards

### Prerequisites
This project requires Node.js (v20+) and npm/pnpm/yarn.

### Setup
Follow these steps to initialize the development environment:

bash
# 1. Clone the repository
git clone https://github.com/chirag127/OmniPublisher-MultiPlatform-Content-Syndicator.git
cd OmniPublisher-MultiPlatform-Content-Syndicator

# 2. Install dependencies using Node Package Manager
npm install

# 3. Configure necessary Environment Variables (See .env.example)
# Requires API keys for Medium, Hashnode, WordPress, etc.
cp .env.example .env


### Scripts
| Command | Description | Tooling | Status |
| :--- | :--- | :--- | :--- |
| `npm run build` | Compiles TypeScript sources into optimized JavaScript. | tsc/Vite | Primary |
| `npm run lint:check` | Runs Biome to check code style and potential errors. | Biome | Mandatory |
| `npm run format` | Automatically fixes formatting issues using Biome. | Biome | Pre-commit Hook |
| `npm run test:unit` | Executes Vitest for unit and integration tests. | Vitest | Verification |
| `npm run test:e2e` | Runs end-to-end validation using Playwright against staging environments. | Playwright | CI/CD |
| `npm run syndicate` | Executes the core CLI tool for publishing (requires credentials). | Node/CLI | Execution |

### Core Principles

1.  **SOLID:** Applied rigorously, especially Dependency Inversion in the Adapter layer.
2.  **DRY:** Core Markdown parsing and token management must be centralized.
3.  **YAGNI:** Only implement platform adapters when they are explicitly required by configuration.

## 📚 Licensing

This project is licensed under the **Creative Commons Attribution-NonCommercial 4.0 International License (CC BY-NC 4.0)**. See the [LICENSE](LICENSE) file for details.

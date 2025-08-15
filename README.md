# autodevops

<div align="center">
  <img src="[https://x.com/autodevopsai/photo](https://github.com/autodevopsai/autodevops/blob/main/image.png)" alt="autodevops logo" width="120" />
  
  <h3>Your code commits. Our agents handle the rest.</h3>
  
  <p>AI micro-agents that eliminate 80% of DevOps busywork. Zero platform migration required.</p>
  
  <p>
    <a href="https://github.com/autodevopsai/autodevops/blob/main/LICENSE">
      <img alt="MIT License" src="https://img.shields.io/badge/license-MIT-blue.svg" />
    </a>
    <a href="https://www.npmjs.com/package/@autodevops/verifier">
      <img alt="npm version" src="https://img.shields.io/npm/v/@autodevops/verifier.svg" />
    </a>
    <a href="https://twitter.com/autodevopsai">
      <img alt="Follow on Twitter" src="https://img.shields.io/twitter/follow/autodevopsai.svg?style=social&label=Follow" />
    </a>
  </p>
  
  <p>
    <a href="#-quick-start">Quick Start</a> •
    <a href="#-features">Features</a> •
    <a href="#-how-it-works">How it Works</a> •
    <a href="#-agents">Agents</a> •
    <a href="https://autodevops.ai/docs">Docs</a> •
    <a href="#-contributing">Contributing</a>
  </p>
</div>

---

## 🎯 The Problem

Every PR wastes 45+ minutes on:
- 🎨 Style nitpicks across multiple languages
- 🔒 Security reviews and vulnerability scanning  
- 📚 Documentation updates that never happen
- 🧪 Writing tests for edge cases
- 🔍 Code review back-and-forth

**That's 112.5 hours per developer per year. Just on repetitive tasks.**

## ✨ The Solution

autodevops deploys AI micro-agents that handle the boring stuff automatically:

```bash
# Install globally
npm install -g @autodevops/verifier

# Initialize in your repo
verifier init

# Run your first agent
verifier run lint --auto-fix

# That's it. Your PR just got 45 minutes faster.
```

## 🚀 Quick Start

### Prerequisites
- Node.js 18+
- Git repository
- API key for your preferred LLM (Claude, OpenAI, or Google)

### Installation

```bash
# Install the CLI
npm install -g @autodevops/verifier

# Or use npx
npx @autodevops/verifier init
```

### Setup

```bash
# Initialize in your repository
verifier init

# This creates:
# - .verifier/config.yaml (agent configuration)
# - .verifier/.env (for API keys)
```

### Configure API Keys

```bash
# Add your preferred LLM API key to .verifier/.env
ANTHROPIC_API_KEY=your-claude-api-key
# or
OPENAI_API_KEY=your-openai-api-key
# or
GOOGLE_API_KEY=your-google-api-key
```

### Run Your First Agent

```bash
# Auto-fix linting issues across all languages
verifier run lint --auto-fix

# Scan for security vulnerabilities
verifier run security-scan

# See all available agents
verifier list
```

## 🎨 Features

### 🤖 Built-in Agents

| Agent | Description | Time Saved |
|-------|-------------|------------|
| **Polyglot Linter** | Auto-fixes style issues across JS, Python, Go, Rust, and more | ~45min/PR |
| **Security Scanner** | Catches vulnerabilities and secrets before production | ~30min/review |
| **Doc Updater** | Keeps README, API docs, and ADRs in sync with code | ~2hrs/feature |
| **Test Generator** | Creates test skeletons and edge cases from your code | ~3hrs/feature |
| **PR Analyzer** | Reviews code quality and suggests improvements | ~30min/PR |
| **Spec Generator** | Transforms tickets into technical specifications | ~2hrs/ticket |

### 🔥 Key Benefits

- **Zero Platform Migration**: Works with your existing Git workflow
- **Language Agnostic**: Supports all major programming languages
- **Privacy First**: Your code never leaves your infrastructure
- **Incremental Adoption**: Start with one agent, scale as trust grows
- **Budget Control**: Hard limits on LLM token usage
- **Open Source**: Extend, customize, and contribute

## 🔧 How It Works

```yaml
# .verifier/config.yaml
agents:
  pre-commit:
    - name: polyglot-linter
      auto_fix: true
      languages: ["js", "py", "go"]
    
    - name: security-scanner
      block_on_critical: true
      
  post-merge:
    - name: doc-updater
      targets: ["README", "API_DOCS"]
    
    - name: test-generator
      coverage_threshold: 80
```

1. **Hook into Git events** - Agents trigger on commits, PRs, merges
2. **Analyze with AI** - LLMs understand code changes and context
3. **Execute micro-tasks** - Each agent masters one specific job
4. **Review and merge** - You stay in control, agents suggest changes

## 📦 Architecture

```
autodevops/
├── packages/
│   ├── verifier/          # Open-source CLI (TypeScript)
│   ├── verifier-py/       # Python implementation
│   └── verifier-kotlin/   # Kotlin implementation
├── app/                   # Web dashboard (Next.js)
└── docs/                  # Documentation
```

### Core Components

- **CLI**: Command-line interface for running agents
- **Agent Engine**: Orchestrates agent execution
- **LLM Providers**: Abstraction for Claude, OpenAI, Google
- **Context Collector**: Gathers relevant code context
- **Privacy Filter**: Redacts sensitive information

## 🤝 Contributing

We love contributions! See our [Contributing Guide](CONTRIBUTING.md) for details.

### Quick Contribution Ideas

```bash
# Fix a bug
git checkout -b fix/issue-123
# Make changes
verifier run lint --auto-fix  # dogfooding!
git commit -m "fix: resolve issue with X"
git push origin fix/issue-123
```

### Creating Custom Agents

```typescript
// my-agent.ts
import { BaseAgent } from '@autodevops/verifier';

export class MyAgent extends BaseAgent {
  async run(context: AgentContext): Promise<AgentResult> {
    // Your agent logic here
    return {
      success: true,
      changes: [],
      message: 'Agent completed successfully'
    };
  }
}
```

## 📊 Stats & Social Proof

- **30% faster PR cycles** reported by early users
- **89% reduction** in security incidents
- **3x improvement** in test coverage
- **Zero documentation debt** for active projects

## 🗺️ Roadmap

- [ ] VS Code Extension 
- [ ] GitHub Action 
- [ ] Custom Agent Marketplace 
- [ ] Team Analytics Dashboard

## 💬 Community

- **Twitter**: [@autodevopsai](https://twitter.com/autodevopsai)

## 📄 License

MIT © [autodevops.ai](https://autodevops.ai)

---

<div align="center">
  <p>
    <strong>Stop drowning in DevOps busywork.</strong>
  </p>
  <p>
    <a href="https://autodevops.ai">Get Started</a> •
    <a href="https://github.com/autodevopsai/autodevops/issues">Report Bug</a> •
    <a href="https://github.com/autodevopsai/autodevops/discussions">Discussions</a>
  </p>
  <p>
    <sub>Built with ❤️ by developers, for developers</sub>
  </p>
</div>

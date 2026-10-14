<!-- TLP:CLEAR -->
# DCYFR AI Sandbox - Quick Start Guide

Welcome to the DCYFR AI Sandbox! This repository is your playground for experimenting with the DCYFR AI harness.

## 🚀 Getting Started

### 1. Install Dependencies

```bash
cd dcyfr-ai-sandbox
npm install
```

Requires Node `>=24.13.0` and npm `>=11.6.2`.

### 2. Run Examples

Try the included examples to see the framework in action:

```bash
# Basic usage example
npm run example:basic

# Plugin system demonstration
npm run example:plugins

# Agent patterns
npm run example:agents
```

### 3. Run Tests

```bash
# Run all tests once
npm run test:run

# Watch mode for development
npm test

# Generate coverage report
npm run test:coverage
```

## 📚 What's Inside

- **examples/** - Three small scripts (`basic-usage.js` runs `PluginLoader`; the other two are stubs)
- **tests/** - A placeholder integration suite

There is no `src/` directory yet.

## 🧪 Experimentation Areas

### Plugin Development
Load plugins through `PluginLoader` and check them with `ValidationFramework` (both exported by `@dcyfr/ai`). See the plugin guide linked below for the plugin interface.

### Agent Patterns
Experiment with different agent implementations:
```typescript
import { PluginLoader } from '@dcyfr/ai';

const loader = new PluginLoader({
  plugins: ['my-validator'],
  telemetry: { enabled: true }
});
```

### Performance Testing
No benchmark scripts exist yet; add your own under a `benchmarks/` directory.

## 🔗 Resources

- [Main Documentation](https://github.com/dcyfr-labs/dcyfr-ai/blob/main/README.md)
- [Plugin System Guide](https://github.com/dcyfr-labs/dcyfr-ai/blob/main/docs/PLUGINS.md)

## 💡 Tips

1. **Start Simple** - Begin with the basic examples
2. **Experiment Freely** - This is a sandbox, break things and learn
3. **Share Discoveries** - Document useful patterns you find
4. **Test Thoroughly** - Use the test suite to validate ideas

## 🤝 Need Help?

- Check the main [@dcyfr/ai documentation](https://github.com/dcyfr-labs/dcyfr-ai)
- Review existing [examples](../examples)
- Explore the [test suite](../tests)

---

Happy experimenting! 🎉

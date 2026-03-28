# Contributing to TRust

Thank you for your interest in contributing! This guide will help you get started, whether you're new to AI-assisted development or an experienced practitioner.

## Table of Contents

1. [BMAD Method: A Beginner's Guide](#bmad-method-a-beginners-guide)
2. [Project Workflow](#project-workflow)
3. [Contribution Types](#contribution-types)
4. [Getting Started](#getting-started)
5. [Need Help?](#need-help)

---

## BMAD Method: A Beginner's Guide

TRust uses **BMAD Method** (Build More Architect Dreams) for structured, AI-driven development. This section teaches you everything you need to know.

### What is BMAD Method?

BMAD is a framework that organizes AI agents into specialized roles (like a software team) and guides them through structured workflows. Instead of ad-hoc prompting, you follow defined phases with clear outputs.

**Key benefits:**
- ✅ Consistent project structure
- ✅ Clear documentation at every stage
- ✅ Better architecture decisions
- ✅ Easier onboarding for new contributors

### The Four Phases

Every BMAD project goes through these phases:

| Phase | Purpose | Key Outputs |
|-------|---------|-------------|
| **1. Analysis** | Understand the problem, brainstorm solutions | Product Brief (optional), Research notes |
| **2. Planning** | Define what we're building | PRD (Product Requirements Document) |
| **3. Solutioning** | Design how we'll build it | Architecture Document, ADRs (Architecture Decision Records) |
| **4. Implementation** | Build it story by story | Working code, tests, documentation |

### Choosing Your Track

BMAD offers three tracks based on project complexity:

| Track | Best For | Documents |
|-------|----------|-----------|
| **Quick Flow** | Bug fixes, small features (1-15 stories) | Tech-spec only |
| **BMad Method** | New products, platforms (10-50+ stories) | PRD + Architecture + UX |
| **Enterprise** | Compliance, multi-tenant systems (30+ stories) | PRD + Architecture + Security + DevOps |

**TRust uses the BMad Method track** (it's a new product with moderate complexity).

### Essential Workflows

BMAD provides 34+ workflows. Here are the ones you'll use most:

#### For New Contributors

```
bmad-help
```
**What it does:** Analyzes the project state and tells you exactly what to do next. This is your starting point for every session.

#### For Planning

```
bmad-brainstorming
```
**What it does:** Guides structured ideation. Use when exploring new features or refining the product vision.

```
bmad-create-product-brief
```
**What it does:** Captures the strategic vision in a concise document. Optional but recommended for new products.

```
bmad-create-prd
```
**What it does:** Creates the Product Requirements Document with functional and non-functional requirements.

#### For Architecture

```
bmad-create-architecture
```
**What it does:** Designs the technical architecture, including technology choices, component diagrams, and ADRs.

```
bmad-create-epics-and-stories
```
**What it does:** Breaks down the architecture into epics and implementable stories.

#### For Implementation

```
bmad-dev-story
```
**What it does:** Implements a single story with proper testing and documentation.

```
bmad-code-review
```
**What it does:** Reviews code against best practices and project standards.

### Workflow Outputs

Each workflow generates artifacts in `_bmad-output/`:

| Workflow | Output Location |
|----------|-----------------|
| `bmad-create-product-brief` | `_bmad-output/product-brief.md` |
| `bmad-create-prd` | `_bmad-output/prd.md` |
| `bmad-create-architecture` | `_bmad-output/architecture.md` |
| `bmad-create-epics-and-stories` | `_bmad-output/epics/`, `_bmad-output/stories/` |

### The Agent Team

BMAD simulates a complete development team. Key roles include:

- **Product Manager** — Defines requirements, prioritizes features
- **Architect** — Makes technical decisions, designs systems
- **Developer** — Implements stories, writes tests
- **UX Designer** — Ensures usability, designs interfaces
- **Scrum Master** — Facilitates workflows, removes blockers
- **DevOps Engineer** — Handles deployment, CI/CD
- **Security Engineer** — Reviews for vulnerabilities
- **QA Engineer** — Tests and validates

You don't need to remember all roles — workflows automatically invoke the right agents.

### Example: Starting a New Feature

```bash
# 1. Check what to do next
npx bmad-method bmad-help

# 2. If brainstorming is needed
npx bmad-method bmad-brainstorming

# 3. Create or update the PRD
npx bmad-method bmad-create-prd

# 4. Design architecture changes
npx bmad-method bmad-create-architecture

# 5. Break into stories
npx bmad-method bmad-create-epics-and-stories

# 6. Implement a story
npx bmad-method bmad-dev-story --story=story-001
```

### Tips for Beginners

1. **Start with `bmad-help`** — Always run this first. It tells you what phase the project is in and what to do next.

2. **Don't skip phases** — Each phase builds on the previous one. Analysis → Planning → Solutioning → Implementation.

3. **Read the outputs** — The generated documents in `_bmad-output/` are your project's source of truth.

4. **Iterate** — You can run workflows multiple times. If requirements change, re-run `bmad-create-prd`.

5. **Ask questions** — If a workflow asks for clarification, provide clear answers. This improves output quality.

---

## Project Workflow

### Branch Naming

```
feature/short-description     # New features
fix/short-description         # Bug fixes
docs/short-description        # Documentation only
refactor/short-description    # Code refactoring
```

### Commit Messages

```
type(scope): short description

# Types: feat, fix, docs, refactor, test, chore
# Examples:
feat(terminal): add WebSocket connection handler
fix(session): resolve pane focus issue
docs(bmad): add beginner's guide
```

### Pull Request Process

1. Create a branch following naming conventions
2. Make your changes
3. Run `bmad-code-review` to validate your code
4. Open a PR with description referencing any related issues
5. Wait for review (all PRs require at least one approval)

---

## Contribution Types

### 🎯 Good First Issues

Look for issues labeled `good-first-issue`. These are specifically chosen for new contributors:

- Documentation improvements
- Small bug fixes
- Test additions
- Typo corrections

### 💡 Feature Development

1. Check `_bmad-output/prd.md` for planned features
2. Find or create an issue for the feature
3. Follow the BMad Method workflow

### 🐛 Bug Reports

When reporting bugs, include:

1. Steps to reproduce
2. Expected behavior
3. Actual behavior
4. Environment (OS, Rust version, etc.)
5. Logs or screenshots if relevant

### 📖 Documentation

Documentation is a first-class contribution:

- Fix typos or unclear sections
- Add examples and tutorials
- Improve BMAD Method guides
- Translate documentation

---

## Getting Started

### Prerequisites

- **Rust** 1.70 or later (`rustup` recommended)
- **Node.js** 18+ (for BMAD Method)
- **Git** for version control

### Setup

```bash
# Clone the repository
git clone https://github.com/luminexo/trust.git
cd trust

# Install BMAD Method
npm install -g bmad-method
# or use npx without installing globally
npx bmad-method --version

# Initialize BMAD for this project
npx bmad-method install

# Check project status
npx bmad-method bmad-help
```

### Your First Contribution

```bash
# 1. See what needs to be done
npx bmad-method bmad-help

# 2. Find a good first issue
# Visit: https://github.com/luminexo/trust/issues?q=is:issue+is:open+label:good-first-issue

# 3. Create a branch
git checkout -b feature/your-feature-name

# 4. Make your changes
# ... edit files ...

# 5. Validate your code
npx bmad-method bmad-code-review

# 6. Commit and push
git add .
git commit -m "feat(scope): your feature description"
git push origin feature/your-feature-name

# 7. Open a PR on GitHub
```

---

## Need Help?

### Resources

- **BMAD Method Docs:** https://docs.bmad-method.org
- **Workflow Map:** https://docs.bmad-method.org/reference/workflow-map/
- **BMAD GitHub:** https://github.com/bmad-code-org/BMAD-METHOD
- **BMAD Discord:** https://discord.gg/gk8jAdXWmj

### Community

- **TRust Issues:** For bug reports and feature requests
- **BMAD Discord:** For BMAD-specific questions
- **Discussions:** For general questions and ideas

### Code of Conduct

- Be respectful and inclusive
- Welcome newcomers
- Focus on constructive feedback
- Support learning and growth

---

## Quick Reference

| What you want | Command |
|---------------|---------|
| Check project status | `npx bmad-method bmad-help` |
| Brainstorm ideas | `npx bmad-method bmad-brainstorming` |
| Create PRD | `npx bmad-method bmad-create-prd` |
| Create architecture | `npx bmad-method bmad-create-architecture` |
| Break into stories | `npx bmad-method bmad-create-epics-and-stories` |
| Implement a story | `npx bmad-method bmad-dev-story --story=<id>` |
| Review code | `npx bmad-method bmad-code-review` |

---

Thank you for contributing to TRust! 🌅
# Contributing to Echo-OS

Welcome to the Echo-OS project! We're building an AI-native operating system together, and we need your help.

## Guiding Principles

Echo-OS is built on these commitments:
- **Local-First:** No cloud dependencies, user privacy by default
- **Open Source:** GPL/MIT dual licensing, community ownership
- **User Ownership:** Your data, your AI, your hardware—always
- **Continuity:** Persistent context and relationship as architectural features
- **Pragmatism:** Build what works, then scale it

## How to Contribute

### 1. **Reporting Bugs**
Found an issue? Open a GitHub issue with:
- What you were doing when the bug occurred
- What you expected to happen
- What actually happened
- Environment (OS, model, hardware)
- Reproduction steps if possible

### 2. **Suggesting Features**
Have an idea? Open a GitHub discussion or issue with:
- Problem statement (what are you trying to achieve?)
- Proposed solution (how would it help?)
- Alternative approaches you considered
- Why it aligns with Echo-OS vision

**Note:** We prioritize features that support the 5-year roadmap. Check [ECHO_OS_VISION.md](../echo/ECHO_OS_VISION.md) to see if your idea fits a phase.

### 3. **Contributing Code**

#### Setup
```bash
git clone https://github.com/sirspyr0/echo
cd echo
npm install                    # For Electron/JavaScript
# or
pip install -r requirements.txt # For Python components
```

#### Workflow
1. **Fork the repository**
2. **Create a feature branch:** `git checkout -b feature/your-feature`
3. **Make your changes** (see Code Style below)
4. **Test thoroughly** (see Testing below)
5. **Commit with clear messages:**
   ```
   Fix: Brief description of change
   
   - Bullet point about implementation
   - Another implementation detail
   - Related issue: #123
   ```
6. **Push and open a Pull Request**
7. **Respond to review feedback** (collaborative process)

#### Code Style
- **JavaScript:** Use ES6+, no JSX (use React.createElement)
- **Python:** Follow PEP 8, use type hints where helpful
- **Documentation:** Clear comments for complex logic
- **Commits:** Atomic (one feature/fix per commit)

#### Testing
Before opening a PR:
```bash
npm run test          # Run test suite
npm start            # Run locally and test UI/UX
npm run build        # Verify build works
```

If adding new features:
- Add unit tests for logic
- Test on multiple hardware (if hardware-specific)
- Document expected behavior

### 4. **Contributing Documentation**

Documentation is as important as code. Help improve:
- **README.md** - Getting started guide
- **CONTRIBUTING.md** (this file) - Contributor guidelines
- **Architecture docs** - Technical deep dives
- **Roadmap clarification** - Phase timeline/milestones
- **Examples & tutorials** - How-to guides

Process:
1. Edit the markdown file
2. Open a PR with: "Docs: Brief description"
3. We'll review for clarity and accuracy

### 5. **Research & Theory**

Echo-OS is grounded in the [Continuity Theory of Consciousness](https://github.com/sirspyr0/ai-continuity-system). If you're interested in the underlying theory:

- Read [ai-continuity-system](https://github.com/sirspyr0/ai-continuity-system) repository
- Open discussions about continuity, relationship, and persistent context
- Propose experiments or validations
- Write papers or blog posts

---

## Project Structure

```
echo/
├── src/                    # Electron renderer (UI)
│   ├── renderer.js        # React UI components
│   ├── index.html         # App shell
├── main.js                # Electron main process (IPC handlers)
├── preload.js             # IPC bridge
├── data/                  # Persistent data
│   ├── programmes.jsonl   # Interaction dataset (for LoRA training)
│   ├── relationship_log.jsonl
│   ├── knowledge_base.json
│   └── oracle.db          # Semantic search index
├── ECHO_OS_VISION.md      # 5-year roadmap (north star)
├── PROJECT_CONTEXT.md     # Technical context for developers
└── package.json           # Dependencies
```

## Current Priorities (Phase 0)

**Happening now:**
- LoRA personality training on programmes.jsonl dataset
- Echo-shell design (intelligent terminal interface)
- Community feedback on ECHO_OS_VISION.md

**We need help with:**
1. **LoRA Fine-Tuning:** Training Echo's personality on 200+ conversations
2. **Echo-Shell Prototype:** Design terminal with AI awareness
3. **Documentation:** Clarifying architecture for newcomers
4. **Testing:** Running Echo locally, reporting bugs/UX issues

---

## Code of Conduct

We're committed to creating an inclusive community.

**We welcome:**
- ✅ Diverse perspectives and experience levels
- ✅ Questions and learning together
- ✅ Respectful disagreement
- ✅ Giving credit to previous work

**We don't tolerate:**
- ❌ Harassment or discrimination
- ❌ Exclusion based on background
- ❌ Plagiarism or IP theft
- ❌ Deliberate misinformation

**Report violations:** Contact us at sirspyr0@github.com or open a private security report.

---

## Review Process

When you open a PR:

1. **Automated checks:** CI/CD pipeline verifies code style, tests, build
2. **Code review:** Maintainers (or experienced contributors) review for:
   - Alignment with Echo-OS vision
   - Code quality and clarity
   - Test coverage
   - Performance implications
3. **Feedback cycle:** We'll suggest changes or approve
4. **Merge:** Once approved, changes are merged to main

**Typical timeline:** 3-7 days for review (we're volunteers!)

---

## Getting Help

Stuck? Questions? Reach out:

- **GitHub Discussions:** https://github.com/sirspyr0/echo/discussions
- **GitHub Issues:** https://github.com/sirspyr0/echo/issues (bugs/features)
- **Email:** sirspyr0@github.com
- **Discord/Community:** [Coming soon—join discussions for updates]

---

## Licensing

By contributing to Echo-OS, you agree that:
- Documentation contributions are licensed under **CC-BY-4.0**
- Code contributions are dual-licensed under **GPL-3.0** and **MIT**
- You retain copyright to your work
- You're okay with your contributions being used under those licenses

See [LICENSE.md](./LICENSE.md) for details.

---

## Recognition

Contributors are recognized in:
- **CONTRIBUTORS.md** (maintained in main repo)
- **GitHub Contributors tab**
- **Release notes** (if your PR is in a release)

We believe in sharing credit. Your contributions matter.

---

## Questions?

Open a GitHub issue labeled `question` or start a discussion. We're here to help.

**Welcome to the project.** Let's build this together. 🚀

---

**Last Updated:** December 22, 2025
**Version:** 1.0

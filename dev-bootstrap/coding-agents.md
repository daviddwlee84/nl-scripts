# Coding Agent Setup Guide

Make sure the following tools are properly installed. Otherwise, please install them properly and test them work.

(you can ask user to use which way to install. e.g. setup script or Homebrew)

If require Node.js, please install the latest LTS version

Coding Agents

- Claude Code
  - `curl -fsSL https://claude.ai/install.sh | bash`
  - `brew install --cask claude-code`
- OpenCode
  - `curl -fsSL https://opencode.ai/install | bash`
  - `brew install anomalyco/tap/opencode`

Agent Companions

- [SpecStory](https://specstory.com/specstory-cli)
  - `brew tap specstoryai/tap` `brew install specstory`
  - Manually download binary from: `https://github.com/specstoryai/getspecstory/releases/`
- Happy
  - `npm install -g happy-coder`

---

Optional

- [Cursor Agent CLI](https://cursor.com/blog/cli)
  - `curl https://cursor.com/install -fsSL | bash`
- Gemini CLI
  - `npm install -g @google/gemini-cli`
- Codex CLI
  - `npm i -g @openai/codex`
- [GitHub Copilot CLI](https://docs.github.com/en/copilot/how-tos/set-up/install-copilot-cli)
  - `brew install copilot-cli`

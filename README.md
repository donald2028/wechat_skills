# WeChat Skills

A collection of skills for Claude Code, Codex, and other AI agents, specializing in WeChat content workflows and creative asset generation.

## 🚀 Installation

### Claude Code plugin

```bash
claude plugin marketplace add donald2028/wechat_skills
claude plugin install wechat-skills@wechat-skills
```

### Codex plugin

```bash
codex plugin marketplace add donald2028/wechat_skills
codex plugin add wechat-skills@wechat-skills
```

When publishing an update, bump the `version` in both plugin manifests.

### Skills CLI

If you have the `skills` CLI installed, you can add this entire collection with one command:

```bash
npx skills add donald2028/wechat_skills -g
```

### Manual installation for OpenCode

To use these skills in your OpenCode environment:

1. **Clone this repository** to your local config directory:
   ```bash
   git clone https://github.com/donald2028/wechat_skills.git ~/.config/opencode/my-skills
   ```

2. **Create a symlink** to make the skills discoverable:
   ```bash
   mkdir -p ~/.config/opencode/skills
   ln -sf ~/.config/opencode/my-skills/skills ~/.config/opencode/skills/my-collection
   ```

3. **Restart your agent** or refresh the skill list.

---

## 🛠 Available Skills

| Skill | Description |
|-------|-------------|
| **[ai-inspiration-scout](./skills/ai-inspiration-scout)** | Search the last 1-2 days of AI news, X discussions, top voices, and GitHub trending tools, then save multiple writing-ready topic ideas into the repo-level `content_hub/01-ideas/`. |
| **[wechat-official-account-manager](./skills/official_accounts)** | Produce, illustrate, format, and sync articles to a WeChat Official Account draft box. |
| **[wechat-article-crawler](./skills/wechat-article-crawler)** | Crawl WeChat official account articles and export full content (Markdown/HTML) plus local assets (images, videos, audio). |
| **[wechat-sticker-generator](./skills/wechat-sticker-generator)** | Generate WeChat-compliant sticker sets (GIF/PNG) with consistent characters and automated background removal. |

---

## 📖 Skill Details

### 1. WeChat Article Crawler
Automatically archive WeChat public account articles with high fidelity.
- **Trigger**: "Crawl this WeChat article", "Save the images from this WeChat link", "Search for WeChat articles about..."
- **Features**: 
  - Extracts title, author, and full content.
  - Downloads images, videos, and audio to local directories.
  - Generates both Markdown and HTML exports.

### 2. WeChat Sticker Generator
Create professional-grade sticker packs for WeChat from text descriptions or personal photos.
- **Trigger**: "Make a sticker pack", "Turn this photo into a chibi sticker", "Create a GIF emoji of a cat dancing."
- **Features**:
  - Supports 12+ art styles (Anime, 3D Clay, Pixel Art, etc.).
  - Automatic background removal and sprite sheet slicing.
  - Generates a full `wechat_export` folder ready for the WeChat platform.

### 3. AI Inspiration Scout
Find daily AI writing angles for creators who need fresh topics quickly.
- **Trigger**: "I need AI topic ideas", "Search the latest AI news", "What is X talking about in AI?", "Any AI tools on GitHub trending worth covering?"
- **Features**:
  - Looks across recent AI news, X platform discussion, top industry voices, and GitHub trending tools.
  - Clusters raw links into 5-10 writing-ready topic candidates.
  - Saves `daily-overview.md`, `idea.md`, and `sources.md` directly into the repo-level `content_hub`.

---

## 🔐 Security & Configuration

Some skills require API keys (e.g., Gemini or DashScope for sticker generation). 

- **Environment Variables**: We recommend setting these in your `.bashrc` or `.zshrc`:
  ```bash
  export GEMINI_API_KEY="your_key_here"
  export DASHSCOPE_API_KEY="your_key_here"
  ```
- **Local Config**: Some skills might use `~/.config/` for local persistence.

---

## 📄 License

MIT License. See [LICENSE](LICENSE) for details.

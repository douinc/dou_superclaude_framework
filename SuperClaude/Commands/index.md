---
name: index
description: "Generate MkDocs documentation site with comprehensive project analysis and intelligent organization"
category: special
complexity: standard
mcp-servers: [sequential, context7, deepwiki]
personas: [architect, scribe, quality]
---

# /sc:index - MkDocs Documentation Generator

## Triggers
- MkDocs documentation site creation and maintenance requirements
- Knowledge base generation with web-friendly navigation
- API documentation and structure analysis for documentation websites
- Cross-referencing and searchable documentation enhancement requests

## Usage
```
/sc:index [target] [--type mkdocs|api|structure|readme] [--theme material|readthedocs] [--plugins auto|minimal|full]
```

## Behavioral Flow
1. **Analyze**: Examine project structure and identify documentation components
2. **Structure**: Create docs/ directory with logical organization and navigation
3. **Configure**: Generate mkdocs.yml with appropriate plugins and theme configuration
4. **Generate**: Create comprehensive Markdown documentation with cross-references
5. **Validate**: Ensure MkDocs compatibility and build verification
6. **Serve**: Provide commands for local development and deployment

Key behaviors:
- Multi-persona coordination (architect, scribe, quality) for comprehensive documentation workflows
- Sequential MCP integration for systematic project analysis and structured documentation generation
- Context7 MCP integration for framework-specific patterns and MkDocs best practices
- Intelligent MkDocs structure with navigation, plugins, and theme optimization

## MCP Integration
- **DeepWiki MCP**: Framework analysis and comprehensive documentation patterns
- **Sequential MCP**: Systematic project analysis and MkDocs site generation workflow
- **Context7 MCP**: MkDocs best practices, Material theme patterns, and plugin configurations
- **Persona Coordination**: Architect (site structure), Scribe (content generation), Quality (build validation)

## Tool Coordination
- **Read/Grep/Glob**: Project analysis and code documentation extraction for MkDocs content
- **Write**: MkDocs configuration, navigation structure, and Markdown documentation generation
- **Bash**: MkDocs installation, build verification, and local development server setup
- **TodoWrite**: Progress tracking for complex multi-phase documentation site creation
- **Task**: Advanced delegation for large-scale documentation requiring systematic MkDocs workflows

## Key Patterns
- **MkDocs Structure**: docs/ directory → index.md → organized sections → navigation configuration
- **Configuration Generation**: mkdocs.yml → theme selection → plugin integration → build optimization
- **Content Organization**: Project analysis → documentation mapping → cross-referencing → search integration
- **Build Workflow**: Site generation → validation → serving → deployment preparation

## MkDocs Configuration Template
```yaml
site_name: "Project Documentation"
site_description: "Comprehensive project documentation and API reference"
site_url: ""
repo_url: ""
repo_name: ""

theme:
  name: material
  palette:
    - media: "(prefers-color-scheme: light)"
      scheme: default
      primary: indigo
      accent: indigo
      toggle:
        icon: material/brightness-7
        name: Switch to dark mode
    - media: "(prefers-color-scheme: dark)"
      scheme: slate
      primary: indigo
      accent: indigo
      toggle:
        icon: material/brightness-4
        name: Switch to light mode
  features:
    - navigation.tabs
    - navigation.sections
    - navigation.expand
    - navigation.top
    - search.highlight
    - search.share
    - content.code.copy
    - content.action.edit

plugins:
  - search:
      separator: '[\s\-,:!=\[\]()"`/]+|\.(?!\d)|&[lg]t;|(?!\b)(?=[A-Z][a-z])'
  - mermaid2:
      arguments:
        theme: |
          ^(JSON.parse(localStorage.getItem('/__palette')).index == 1) ? 'dark' : 'light'
  - git-revision-date-localized:
      enable_creation_date: true
  - minify:
      minify_html: true
  - awesome-pages

markdown_extensions:
  - abbr
  - admonition
  - attr_list
  - def_list
  - footnotes
  - md_in_html
  - toc:
      permalink: true
  - pymdownx.arithmatex:
      generic: true
  - pymdownx.betterem:
      smart_enable: all
  - pymdownx.caret
  - pymdownx.details
  - pymdownx.emoji:
      emoji_generator: !!python/name:material.extensions.emoji.to_svg
      emoji_index: !!python/name:material.extensions.emoji.twemoji
  - pymdownx.highlight:
      anchor_linenums: true
      line_spans: __span
      pygments_lang_class: true
  - pymdownx.inlinehilite
  - pymdownx.keys
  - pymdownx.magiclink:
      normalize_issue_symbols: true
      repo_url_shorthand: true
      user: ""
      repo: ""
  - pymdownx.mark
  - pymdownx.smartsymbols
  - pymdownx.snippets:
      auto_append:
        - includes/mkdocs.md
  - pymdownx.superfences:
      custom_fences:
        - name: mermaid
          class: mermaid
          format: !!python/name:pymdownx.superfences.fence_code_format
  - pymdownx.tabbed:
      alternate_style: true
      combine_header_slug: true
  - pymdownx.tasklist:
      custom_checkbox: true
  - pymdownx.tilde

extra:
  social:
    - icon: fontawesome/brands/github
      link: ""
    - icon: fontawesome/brands/python
      link: ""
  generator: false

nav:
  - Home: index.md
  - Getting Started:
    - Installation: getting-started/installation.md
    - Quick Start: getting-started/quick-start.md
    - Configuration: getting-started/configuration.md
  - User Guide:
    - Overview: user-guide/index.md
    - Basic Usage: user-guide/basic-usage.md
    - Advanced Features: user-guide/advanced-features.md
  - API Reference:
    - Overview: api/index.md
  - Developer Guide:
    - Contributing: developer-guide/contributing.md
    - Architecture: developer-guide/architecture.md
  - Reference:
    - Changelog: reference/changelog.md
    - FAQ: reference/faq.md
```

## Examples

### Complete MkDocs Site Generation
```
/sc:index . --type mkdocs --theme material --plugins full
# Complete MkDocs site with docs/ directory, mkdocs.yml, and comprehensive content
# Material theme with full plugin suite including Mermaid, search, and git integration
```

### API Documentation Site
```
/sc:index src/api --type api --theme material --plugins auto
# API-focused MkDocs site with automatic plugin selection
# Scribe and quality personas ensure comprehensive API documentation
```

### Minimal Documentation Site
```
/sc:index . --type mkdocs --theme readthedocs --plugins minimal
# Clean MkDocs site with ReadTheDocs theme and essential plugins only
# Architect persona provides optimal structure for simple documentation needs
```

## Installation Requirements
The command will automatically install required MkDocs dependencies:

```bash
# Core MkDocs
pip install mkdocs

# Material Theme
pip install mkdocs-material

# Essential Plugins
pip install mkdocs-mermaid2-plugin
pip install mkdocs-git-revision-date-localized-plugin
pip install mkdocs-minify-plugin
pip install mkdocs-awesome-pages-plugin

# Alternative: Install all at once
pip install mkdocs mkdocs-material mkdocs-mermaid2-plugin mkdocs-git-revision-date-localized-plugin mkdocs-minify-plugin mkdocs-awesome-pages-plugin
```

## Development Commands
After generation, use these commands for MkDocs development:

```bash
# Serve locally with live reload
mkdocs serve

# Build static site
mkdocs build

# Deploy to GitHub Pages
mkdocs gh-deploy
```

## Boundaries

**Will:**
- Generate complete MkDocs documentation sites with proper directory structure and configuration
- Create comprehensive mkdocs.yml with appropriate themes, plugins, and markdown extensions
- Apply multi-persona coordination for systematic site structure and content validation
- Provide MkDocs best practices and Material theme optimization

**Will Not:**
- Override existing MkDocs configuration without explicit update permission
- Generate documentation sites without proper MkDocs compatibility validation
- Bypass MkDocs plugin requirements or theme-specific configuration standards

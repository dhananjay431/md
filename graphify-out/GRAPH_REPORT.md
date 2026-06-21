# Graph Report - .  (2026-06-21)

## Corpus Check
- Corpus is ~2,389 words - fits in a single context window. You may not need a graph.

## Summary
- 37 nodes · 61 edges · 7 communities
- Extraction: 97% EXTRACTED · 3% INFERRED · 0% AMBIGUOUS · INFERRED: 2 edges (avg confidence: 0.9)
- Token cost: 0 input · 33,595 output

## Community Hubs (Navigation)
- [[_COMMUNITY_Markdown Rendering Pipeline|Markdown Rendering Pipeline]]
- [[_COMMUNITY_Layout & Sync Scroll|Layout & Sync Scroll]]
- [[_COMMUNITY_Theme Selectors & Persistence|Theme Selectors & Persistence]]
- [[_COMMUNITY_Button Actions|Button Actions]]
- [[_COMMUNITY_Share via Base64 Link|Share via Base64 Link]]
- [[_COMMUNITY_Theme Switching|Theme Switching]]
- [[_COMMUNITY_Mermaid Integration|Mermaid Integration]]

## God Nodes (most connected - your core abstractions)
1. `localStorage persistence` - 10 edges
2. `initButtons` - 8 edges
3. `initThemeSelectors` - 8 edges
4. `init (orchestrator)` - 7 edges
5. `render (markdown->HTML pipeline)` - 7 edges
6. `initEditor` - 5 edges
7. `initSyncScroll` - 4 edges
8. `rerenderMermaid` - 4 edges
9. `setTheme` - 4 edges
10. `getMarkdown` - 4 edges

## Surprising Connections (you probably didn't know these)
- `init (orchestrator)` --calls--> `initButtons`  [EXTRACTED]
  index.html → index.html  _Bridges community 1 → community 3_
- `init (orchestrator)` --calls--> `initEditor`  [EXTRACTED]
  index.html → index.html  _Bridges community 1 → community 0_
- `init (orchestrator)` --calls--> `initThemeSelectors`  [EXTRACTED]
  index.html → index.html  _Bridges community 1 → community 2_
- `init (orchestrator)` --calls--> `initThemeToggle`  [EXTRACTED]
  index.html → index.html  _Bridges community 1 → community 5_
- `initEditor` --calls--> `getMarkdown`  [EXTRACTED]
  index.html → index.html  _Bridges community 0 → community 4_

## Import Cycles
- None detected.

## Hyperedges (group relationships)
- **Markdown render pipeline (parse -> sanitize -> highlight -> mermaid)** — markdown_index_render, markdown_index_marked_renderer, markdown_index_dompurify_sanitizer, markdown_index_highlightcode, markdown_index_rendermermaid [EXTRACTED 1.00]
- **Theme system (toggle + code/mermaid selectors + re-render)** — markdown_index_settheme, markdown_index_initthemetoggle, markdown_index_initthemeselectors, markdown_index_applycodetheme, markdown_index_rerendermermaid, markdown_index_resolvemermaidtheme [EXTRACTED 1.00]
- **Share subsystem (encode -> URL -> decode on load)** — markdown_index_getmarkdown, markdown_index_base64urltoutf8, markdown_index_utf8tobase64url, markdown_index_initbuttons [EXTRACTED 1.00]

## Communities (7 total, 0 thin omitted)

### Community 0 - "Markdown Rendering Pipeline"
Cohesion: 0.29
Nodes (7): CodeMirror editor integration, decodeEntities, DOMPurify HTML sanitizer, escapeHtml, highlightCode, initEditor, render (markdown->HTML pipeline)

### Community 1 - "Layout & Sync Scroll"
Cohesion: 0.29
Nodes (7): init (orchestrator), initSplit, initSyncScroll, marked markdown renderer, ratioScroll, Split-pane divider, Sync scroll feature

### Community 2 - "Theme Selectors & Persistence"
Cohesion: 0.60
Nodes (6): applyCodeTheme, getCodeTheme, getMermaidThemePref, highlight.js syntax highlighting, initThemeSelectors, localStorage persistence

### Community 3 - "Button Actions"
Cohesion: 0.70
Nodes (5): fallbackCopy, fallbackShare, flash, PNG export via html2canvas, initButtons

### Community 4 - "Share via Base64 Link"
Cohesion: 0.83
Nodes (4): base64UrlToUtf8, getMarkdown, Share via base64 URL (?text=), utf8ToBase64Url

### Community 5 - "Theme Switching"
Cohesion: 0.67
Nodes (4): Early theme bootstrap (FOUC prevention), initThemeToggle, setTheme, Theme switching (dark/light + code/mermaid themes)

### Community 6 - "Mermaid Integration"
Cohesion: 0.67
Nodes (4): Mermaid diagram integration, renderMermaid, rerenderMermaid, resolveMermaidTheme

## Knowledge Gaps
- **8 isolated node(s):** `escapeHtml`, `decodeEntities`, `ratioScroll`, `CodeMirror editor integration`, `DOMPurify HTML sanitizer` (+3 more)
  These have ≤1 connection - possible missing edges or undocumented components.

## Suggested Questions
_Questions this graph is uniquely positioned to answer:_

- **Why does `localStorage persistence` connect `Theme Selectors & Persistence` to `Markdown Rendering Pipeline`, `Layout & Sync Scroll`, `Button Actions`, `Share via Base64 Link`, `Theme Switching`?**
  _High betweenness centrality (0.342) - this node is a cross-community bridge._
- **Why does `init (orchestrator)` connect `Layout & Sync Scroll` to `Markdown Rendering Pipeline`, `Theme Selectors & Persistence`, `Button Actions`, `Theme Switching`?**
  _High betweenness centrality (0.296) - this node is a cross-community bridge._
- **Why does `initButtons` connect `Button Actions` to `Layout & Sync Scroll`, `Theme Selectors & Persistence`, `Share via Base64 Link`?**
  _High betweenness centrality (0.276) - this node is a cross-community bridge._
- **What connects `escapeHtml`, `decodeEntities`, `ratioScroll` to the rest of the system?**
  _8 weakly-connected nodes found - possible documentation gaps or missing edges._
# PoliteDB docs

This repository contains the product documentation for PoliteDB.

This README focuses on **docs content**: what to write, where to write it, and how to keep it consistent.

## Content map

Use this structure when deciding where new content should live:

- `index.mdx`: product overview and entry point
- `quickstart.mdx`: first-run path for new users
- `essentials/`: foundational concepts (connections, keychain, workspace, architecture)
- `features/`: focused guides for individual capabilities (SQL editor, safe mode, AI assistant, etc.)
- `docs.json`: information architecture and sidebar order

Rule of thumb:

- If users must understand a concept before using features, write it in `essentials/`.
- If users want task-oriented guidance for one capability, write it in `features/`.

## Writing principles

- Write for operators who need clear, actionable guidance.
- Use active voice and second person ("you").
- Keep one idea per sentence.
- Prefer concrete behavior over vague claims.
- Explain constraints and safety implications clearly.

## Page template

For most pages, keep this flow:

1. **What it is**: short definition and when to use it.
2. **How it works**: behavior users can expect in app.
3. **Key workflows**: practical, common tasks.
4. **Safety/limits**: what it does not do, and where to be careful.
5. **Recommended usage**: when to choose this feature or mode.

## Style conventions

- Use sentence case for headings.
- Bold UI elements: Click **Settings**.
- Use code formatting for commands, paths, and identifiers: `mint dev`, `docs.json`, `safe mode`.
- Keep lists short and scannable.
- Avoid marketing language and repeated claims.

## Accuracy requirements

Before publishing changes:

- Verify behavior against implementation in `politedb-app` for feature docs.
- Keep terminology consistent across pages.
- If behavior is conditional (for example by mode), document each mode explicitly.
- Prefer precise wording like "requires Touch ID before sending queries" over generic text like "adds safety."

## Adding a new docs page

1. Create a new `.mdx` file in `essentials/` or `features/`.
2. Add frontmatter:
   - `title`
   - `description`
3. Write content using the page template above.
4. Add the page to `docs.json` navigation.
5. Add images to `images/` and reference with absolute path, for example `/images/main-screen.png`.
6. Validate links and preview formatting before merging.

## Run docs locally

Use this flow to preview docs changes on your machine:

1. Install Mintlify CLI (one-time):

```bash
npm i -g mint
```

2. Start local docs preview from repository root:

```bash
mint dev
```

3. Open local site at `http://localhost:3000`.

4. Check links before merge:

```bash
mint broken-links
```

## Images and examples

- Use product screenshots to clarify UI-heavy flows.
- Place the first image near the intro when it helps orient the reader.
- Keep captions concise and factual.
- Use realistic SQL examples that match documented workflows.

## AI-assisted writing

If you use AI to draft docs, install Mintlify documentation skill:

```bash
npx skills add https://mintlify.com/docs
```

Then review generated content for:

- Product accuracy
- Terminology consistency
- Clarity and brevity

- [Mintlify documentation](https://mintlify.com/docs)

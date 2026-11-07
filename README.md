# BrandLens (Team Star-hacks) – Round 2 build

Pre-publication brand review: checks a draft against approved guidelines, facts and terminology, explains each finding with its source, suggests fixes, and keeps humans in control.

## Run it
Open `index.html` in any browser. No install, no server, no API keys.
Deploy free: GitHub Pages (Settings → Pages → main branch) or drag the file onto Netlify Drop.

## Working features
- Editable knowledge base (guidelines, approved facts, banned terms)
- Text review: terminology, tone, unsupported claims, outdated facts, missing alt text, long sentences
- Every finding shows reason, severity and source rule/fact (or “unverified”)
- Accept / edit / reject suggestions; nothing is auto-applied
- Roles: Creator, Manager, Reviewer, Admin; submit, approve (with recorded override), request changes
- Comments, version history, audit log
- Colour contrast (WCAG) and palette check
- Optional AI deep review (Claude): finds tone, messaging and claim issues the rules miss; findings cite a listed source or show “unverified”. Works only when opened on claude.ai; elsewhere the rule engine runs alone
- Governance insights: most flagged rules and “guideline may be unclear” flag

## Technical notes
Single-file vanilla JS app. Claim checking uses token overlap between a sentence and approved facts; a number mismatch is reported as “outdated”. No match is reported as “no approved support found”, not as false. State is saved in `localStorage` (per browser, not shared).

## Disclosure
Rule checks need no AI. The optional AI deep review calls Claude (Anthropic) only after the viewer consents. AI assistance (Claude) was used to write the code.

## Not done yet
PDF/DOCX/PPTX/image upload, LLM-based tone and claim review, shared backend and real login, multi-user sync.

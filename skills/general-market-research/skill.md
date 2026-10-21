---
name: general-market-research
description: Conduct structured market and competitive research using Porter's Five Forces, PESTEL, and SWOT frameworks, grounded in real web-researched data about an industry or company. Use this skill whenever the user asks for competitive analysis, industry analysis, market research, "Five Forces", "PESTEL", "SWOT", strategic positioning, "should I enter this market", or wants to understand an industry's attractiveness, competitive dynamics, or a company's strategic position — even if they don't name a specific framework. Make sure to trigger this for requests like "analyze the competitive landscape of X industry," "what are the barriers to entry in Y," or "do a market analysis for my startup idea."
---

# Market Research & Competitive Analysis

Produces rigorous, evidence-based strategic analysis of an industry or company using established frameworks. Default lead framework is Porter's Five Forces; PESTEL and SWOT are used to complement it when relevant.

## Workflow

1. **Clarify scope** (briefly, only if genuinely ambiguous). You need:
   - The industry or market (and geography, if it matters — "EV charging in the US" vs. "EV charging globally")
   - The focal company/product, if the user has one in mind (Five Forces analyzes an industry; SWOT typically analyzes a specific player within it)
   - Which frameworks they want — default to Five Forces alone unless the request implies broader strategic context (e.g. "should we enter this market," "full market research") in which case add PESTEL and/or SWOT
   Don't over-ask — if scope is reasonably clear from the request, proceed and state your interpreted scope up front instead of blocking on questions.

2. **Research before analyzing.** Never fill in framework boxes from general knowledge alone. For each force/factor, run targeted web searches to find current, specific evidence: market concentration/HHI data, recent entrant or exit news, supplier/buyer concentration, switching costs, substitute products gaining share, capital intensity, regulatory changes, recent M&A. Aim for searches specific enough to return real numbers, named companies, or named recent events rather than generic textbook description. Cite sources per Claude's standard citation practice.

3. **Select and read the relevant framework reference(s)** before writing the analysis:
   - `references/five-forces.md` — always read this one (default lead framework)
   - `references/pestel.md` — read if doing macro-environment scanning
   - `references/swot.md` — read if analyzing a specific company/product, not just the industry

4. **Write the analysis** following the structure and rating conventions in those reference files. Always include:
   - A one-paragraph scope statement (industry, geography, time frame, focal company if any)
   - The framework body (each force/factor: evidence → intensity rating → so what)
   - A synthesis: 3-5 sentence "bottom line" — is this an attractive market, what's the dominant force, what does it imply for strategy
   - Note explicitly where evidence was thin or ambiguous, rather than papering over gaps with confident-sounding generic claims

5. **Format as prose with light structure**, not box-checking. Use the five/six headers as organizing structure, but write in paragraphs under each — not bullet fragments — except where the user explicitly wants a scannable list or table (e.g. a force-by-force intensity table is fine as a table).

## Output conventions

- Each force/factor gets an intensity/impact rating (High / Medium / Low) with one sentence justifying the rating before the detailed paragraph — this lets the synthesis be skimmed.
- Don't present Five Forces as purely negative ("threats") — frame each force neutrally as "favorable/unfavorable to industry profitability," since some forces (e.g. low rivalry) can be favorable.
- Flag when forces interact or offset (e.g. high entry barriers but also high rivalry among entrenched incumbents) — this nuance is usually the most valuable part of the analysis and is often missing from generic treatments.
- If the user wants this delivered as a Word document or slide deck rather than inline text, use the docx or pptx skill for formatting — this skill only governs the analytical content and structure.

## When NOT to do a full multi-framework workup

If the user asks a narrow, single-fact question embedded in strategy language (e.g. "what's Porter's five forces?" as a definitional question, or "is the airline industry consolidated?") just answer directly — don't force the full workflow above onto simple factual or definitional questions.


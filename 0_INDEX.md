# Xometry — ML System Design: Worked Designs Index

Round: System Design, 60 min · Jun 26, 2026, 10–11a ET.
Panel: **Karim Abdelkader** (Staff Cloud/MLOps — weight serving, AWS, lifecycle, cost) · **Henrique Oliveira Evangelista** (SWE/ML — clean interfaces, data contracts, testing).

Each doc is standalone: clarify → metrics → architecture (diagram) → deep-dives → serving/MLOps → eval → probes → Xometry angles → questions.

| # | Design | When it's the prompt | File |
|---|--------|----------------------|------|
| 1 | **RAG over manufacturing knowledge** ★ | "build an LLM RAG system" (you were told this is tested) | `1_RAG_manufacturing_knowledge.md` |
| 2 | **Structured extraction from drawings** ★ | the JD core (dimensions/tolerances/GD&T) | `2_drawing_extraction.md` |
| 3 | **Multimodal document understanding** | many doc types → structured data | `3_multimodal_document_understanding.md` |
| 4 | **LLM serving / inference platform** | Karim's deep-dive; serving/scale/cost | `4_llm_serving_platform.md` |
| 5 | **Marketplace ML: quoting + matching** | the business framing (pricing, supplier match) | `5_marketplace_quoting_matching.md` |
| 6 | **Agentic RAG** | "agentic RAG" / multi-tool, multi-hop assistant | `6_agentic_rag.md` |
| ★ | **Sous Chef AI (Karim rapport + worked design)** | rapport with Karim + an agentic-multimodal-RAG analog | `karim_souschef_prep.md` |

Companion: `../Xometry_RAG_Cheatsheet.pdf` (one-page glanceable) and `../Xometry_ML_System_Design_Prep.md` (combined overview + framework + rapid-fire).

**Universal framework to drive (every prompt):** clarify & scope (numbers) → requirements/SLAs → define the output contract → high-level architecture (draw it) → deep-dive the hard parts → scale/cost/latency (quantify) → eval/monitoring/lifecycle → failure modes & what you'd cut.

**Highest-leverage prep:** be able to draw the **RAG flow (#1)** and grow it stage-by-stage while narrating tradeoffs — that's the exact "build an LLM RAG system" signal they flagged.

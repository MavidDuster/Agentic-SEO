# SEO Audit Report: Denkmuster.dev

This is a **single-page** SEO audit conducted for `https://denkmuster.dev/`. The analysis covers on-page metadata, technical signals, content quality, and readiness for AI-driven search (GEO/AEO).

## Audit Summary

- **Scope**: Single-page audit of `https://denkmuster.dev/`
- **Overall Rating**: Good (70-89) – strong foundational on-page SEO, but with clear technical and AI readiness gaps.
- **Top 3 Issues**: 
  1. No JSON-LD Schema (hurts E-E-A-T signals).
  2. Missing `llms.txt` and unmanaged AI crawlers (missed AEO optimization).
  3. No explicit security headers.
- **Top 3 Opportunities**:
  1. Add `Organization` and `Person` schema to establish authority as an AI expert.
  2. Create an `llms.txt` file for RAG consumption.
  3. Sync the meta description with the site's primary language content.

## Score Breakdown

**Score justification:**
Score of 75 reflects strong title tagging, sensible heading structure, and clean internal links (+), penalized by missing JSON-LD schema (Critical, −15) and lack of security headers/AI management rules (Warning, −10).
*(Note: Core Web Vitals score omitted due to API rate limits).*

## Findings

| Area | Severity | Confidence | Finding | Evidence | Fix |
|---|---|---|---|---|---|
| Technical | 🔴 Critical | Confirmed | JSON-LD schema is completely missing. | `parse.json` shows `"schema": []`. | Add `Organization` and `Person` schema to strengthen E-E-A-T signals in search. |
| AI Search (GEO) | 🔴 Critical | Confirmed | Missing `llms.txt` for AI crawlers. | `llms_txt_checker` returned HTTP 404. | Create `/llms.txt` summarizing site expertise, services, and linking key pages. |
| Technical | ⚠️ Warning | Confirmed | Missing canonical link tag. | `parse.json` shows `"canonical": null`. | Add `<link rel="canonical" href="https://denkmuster.dev/" />` to the `<head>`. |
| AI Search (GEO) | ⚠️ Warning | Confirmed | AI crawlers are unmanaged. | `robots.txt` does not explicitly manage `GPTBot`, `ClaudeBot`, etc. | Add explicit allow/disallow rules for major AI bots in `robots.txt`. |
| Technical | ⚠️ Warning | Confirmed | 6 security headers are missing. | `security_headers.py` flagged missing HSTS, CSP, X-Frame-Options, etc. | Configure the web server (or host) to serve modern security headers. |
| Content | ⚠️ Warning | Confirmed | High reading difficulty (Flesch: 40.7). | `readability.json` flagged 25.3% complex words. | Simplify vocabulary limits (reduce 3+ syllable words) and shorten average sentence length where possible. |
| Technical | ⚠️ Warning | Confirmed | Open Graph description differs from Meta Description. | Meta desc is English ("A hub for..."), while OG desc is German ("Wo nicht nur..."). | Sync the meta descriptions for consistency (preferably to German, reflecting the site content). |
| Performance | ⚠️ Warning | Hypothesis | Images lack explicit width/height attributes, risking CLS. | `parse.json` shows "width": null, "height": null for all `<img>` tags. | Specify explicit dimensions (`width` and `height`) in the `<img>` HTML tags. |
| On-Page | ✅ Pass | Confirmed | Title tag is well-optimized. | "Denkmuster.dev \| AI, Ethics & Personal Growth" (45 chars). | Maintain current length. |
| On-Page | ✅ Pass | Confirmed | Logical heading structure. | H1 is exact and descriptive, followed by logical H2s and H3s. | Maintain current structure. |

## Unknowns and Follow-ups

- **Core Web Vitals**: Blocked by Google PageSpeed API rate limits. Requires a manual check via Search Console or Lighthouse.
- **Broken Links**: Sub-pages and external links need an extended crawl to ensure valid HTTP responses.

---

*Generated using Agentic SEO LLM pipeline.*

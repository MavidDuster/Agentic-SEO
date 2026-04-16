# SEO Action Plan: Denkmuster.dev

This action plan is prioritized by SEO impact and implementation effort. Start with Immediate Blockers.

## 1. Immediate Blockers (High Impact, Low Effort)
- **Implement JSON-LD Schema**:
  - Add `Organization` schema to the homepage.
  - Add `Person` schema representing the site owner to boost E-E-A-T signals.
- **Add Canonical Tag**:
  - Include `<link rel="canonical" href="https://denkmuster.dev/" />` in the homepage `<head>` to prevent URL parameter duplication issues.

## 2. Quick Wins (Medium Impact, Low Effort)
- **Create `/llms.txt`**:
  - Add this file to the root directory for AI crawlers (like ChatGPT, Perplexity, Claude). Detail the core proposition ("Piloting AI") and link to the Audit and Training pages.
- **Sync Meta Data**:
  - The current meta description is in English, while the site and OG tag are in German. Standardize the meta description (e.g., "Die meisten AI-Trainings machen dich zum Konsumenten. Ich mache dich zum Piloten. Praxisnah, kritisch, unabhängig.")
- **Image Dimensions**:
  - Add `width` and `height` attributes to the 4 images (SVGs and JPG) to prevent Cumulative Layout Shift (CLS) on load.

## 3. Strategic Improvements (High Impact, Higher Effort)
- **Content Formatting & Readability**:
  - Average paragraph length is currently recognized as very long. Visually break up heavy text blocks into 2-4 sentence chunks to improve user engagement and time-on-site.
  - Reduce the density of complex words (currently 25.3%) to improve the Flesch Reading Ease score.
- **Security Posture**:
  - Implement security headers (HSTS, Content-Security-Policy, X-Frame-Options, X-Content-Type-Options, Referrer-Policy). This is a minor ranking signal but critical for UX and trust.
- **robots.txt AI Rule Management**:
  - Add specific blocks in `robots.txt` regulating how `GPTBot`, `ClaudeBot`, `Google-Extended`, and `Applebot-Extended` crawl your site, establishing control over AI ingestion.

## Schema Suggestions
Here is a base schema template you can insert into your `<head>`:

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "Organization",
      "name": "Denkmuster",
      "url": "https://denkmuster.dev",
      "logo": "https://denkmuster.dev/images/workshop_icon.svg",
      "description": "Ex-Deloitte Berater und JKU AI-Absolvent. Fokus auf AI Auditing und Schulungen."
    },
    {
      "@type": "Person",
      "name": "David Muster",
      "jobTitle": "AI Technical Consultant",
      "url": "https://denkmuster.dev/about",
      "sameAs": [
        "https://www.linkedin.com/in/david-muster-7a7857162/",
        "https://github.com/MavidDuster"
      ]
    }
  ]
}
</script>
```

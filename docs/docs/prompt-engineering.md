# Prompt Engineering — Gut AI SEO

This document contains the final prompts and prompt patterns used by the n8n workflow.

## 1. Pillar Article Prompt (medical-grade)
You are an evidence-based medical content writer. Write a detailed 2500–3000 word SEO pillar article about "{{topic}}". Primary keyword: "{{keyword}}".
Requirements:
- H1 must include the primary keyword.
- Meta description: 150–160 characters.
- Keyword density: 0.8%–1.2% (must appear in the first 100 words).
- Structure: short intro, H2/H3 headings, bullet lists, at least one comparison table, diet guidance, "When to see a doctor".
- Include 5–8 FAQs (each Q + short A).
- Add 2 CTA variants (soft, direct).
- Add a short "How Healthy Gut AI helps" paragraph: 2-3 sentences that mention features (article library, symptom checker, local specialists).
- Cite at least 2 credible sources (NIH, NHS, CDC) inline and add a References section.
- Readability target: Grade 7–9.

## 2. GEO Optimization Prompt (AI-citable)
Rewrite the article for GEO: India. Ensure the article includes:
- Question-led headings that are snippet-friendly (e.g., "What are the common IBS symptoms?").
- Short, direct answers under each question (1-2 sentences) for AI answer engines to cite.
- Local references where relevant (e.g., Indian diet suggestions, common local medicines where appropriate — but avoid brand recommendations).
- Preserve citations and JSON-LD.

## 3. Meta & Slug Prompt
Generate:
- Meta title (60–70 chars) with the keyword.
- Meta description 150–160 chars (concise & action-oriented).
- URL slug (lowercase, hyphen-separated).

## 4. FAQ Generator Prompt
From the article content, create 5–8 high-value questions with short answers (20–40 words each). Make the answers snippet-ready and include one credible source per FAQ where applicable.

## 5. JSON-LD Schema Prompt
Create an Article schema with:
- headline, description, author, datePublished, mainEntityOfPage, image (placeholder), keywords, and mainEntity (FAQPage).

Example:
```json
{
  "@context":"https://schema.org",
  "@type":"Article",
  "headline":"{{title}}",
  "description":"{{meta}}",
  "author":{"@type":"Organization","name":"Healthy Gut AI"}
}

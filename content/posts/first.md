+++
title = "Engineering Journal: Building a Personal Blog Like a Product"
date = 2026-03-10
translation_key = "engineering-journal-product-blog"
authors = ["Auri Gabriel"]
[taxonomies]
categories = ["Development", "Architecture"]
tags = ["zola", "frontend", "ux", "writing"]
[extra]
lead = "A long-form test article about designing a blog with production-quality structure, typography, and developer ergonomics."
+++

When I started this blog I treated it like a side project. After a few iterations, I realized I should treat it like a product: define a clear reading experience, test assumptions with realistic content, and optimize for maintainability. This post is intentionally long so I can evaluate the page style under real-world reading conditions.

## Why this article exists

The initial layout looked acceptable with short content, but real posts quickly exposed issues:

- inconsistent spacing between sections
- weak contrast in long paragraphs
- metadata and taxonomy treatment competing with the article body
- code blocks and tables feeling disconnected from text rhythm

The goal is not to over-design. The goal is to make writing and reading feel calm, structured, and intentional.

## Editorial constraints

To keep this blog maintainable, I use a small set of constraints:

1. Content first: every design decision should improve readability.
2. Predictable hierarchy: headline → deck → body → secondary metadata.
3. Reasonable defaults: no per-post CSS hacks.
4. Progressive enhancement: works without JavaScript for core reading.

> A good blog theme is not one that looks complex. It is one that disappears while the content does the work.

## Example architecture notes

At the project level, I keep a simple structure:

- `templates/` for layout and page composition
- `sass/` for shared visual language
- `content/posts/` for editorial content only

This separation lets me iterate quickly without mixing concerns.

### Build pipeline checklist

Before publishing, I validate these points:

| Check | Why it matters | Status |
| --- | --- | --- |
| `zola build` passes | Prevent broken deploys | ✅ |
| typography on long posts | Real reading comfort | ✅ |
| code blocks on mobile | Developer audience | ✅ |
| metadata clarity | Scannability | ✅ |

## Sample code block for style testing

```rust
#[derive(Debug)]
struct PostMeta {
	title: String,
	reading_time_min: usize,
	tags: Vec<String>,
}

fn estimate_reading_time(words: usize) -> usize {
	let words_per_minute = 220;
	((words as f32) / (words_per_minute as f32)).ceil() as usize
}

fn main() {
	let words = 1420;
	let reading_time = estimate_reading_time(words);
	println!("Estimated reading time: {reading_time} min");
}
```

The code above is not complex, but it is enough to test line height, horizontal overflow behavior, and syntax highlighting balance.

## Paragraph rhythm stress test

This section exists only to verify the vertical rhythm. In practice, technical writing alternates between conceptual explanation and implementation detail. The template needs to support both without creating visual fatigue.

A readable blog body gives breathing room between ideas, but it does not waste space. It should feel deliberate: dense enough for technical readers, open enough for scanning. If a user lands on this page from search, they should be able to quickly find headings, code, and summary points.

Another important detail is link styling. Links should remain visible without looking noisy. Underlines are useful for accessibility and clarity, especially in long documents where color alone is not enough.

### Practical migration note

If you are refactoring a theme, avoid big-bang rewrites. Move in small slices:

1. lock the structure
2. tune typography
3. improve components (cards, taxonomy, metadata)
4. validate with long content

This incremental approach reduces regressions and gives faster feedback loops.

## Final takeaway

This article is intentionally verbose to test layout under realistic conditions. If this page feels stable, readable, and professional, the theme is likely in a good baseline state for real publishing.

Next iteration will focus on author profile blocks, related posts, and subtle improvements to navigation density.

# YTScope Content

This repository contains blog posts and academy articles for [YTScope](https://ytscope.com).

## Structure

```
├── index.yaml          # Content index (required)
├── blog/               # Blog posts
│   └── *.md
└── academy/            # Localized Academy/tutorial articles
    ├── tr/*.mdx
    └── en/*.mdx
```

## Adding New Content

### 1. Create the markdown file

**Blog post:** `blog/your-post-slug.md`
**Academy article:** `academy/{tr|en}/your-article-slug.mdx`

### 2. Add frontmatter

**Blog post:**
```yaml
---
title: "Your Post Title"
description: "SEO description (140-155 chars)"
date: "2025-01-15"
author: "YTScope Team"
readingTime: 5
featured: false
tags: ["youtube", "analytics"]
---
```

**Academy article:**
```yaml
---
title: "Article Title"
description: "SEO description"
lastUpdated: "2025-01-15"
order: 1
---
```

### 3. Update index.yaml

Add your new content to `index.yaml`:

```yaml
blog:
  - slug: your-post-slug
    published: true

academy:
  tr:
    - guideId: stable-guide-identity
      slug: yerel-rehber-adresi
      published: true
      order: 1
  en:
    - guideId: stable-guide-identity
      slug: localized-guide-slug
      published: true
      order: 1
```

`guideId` is locale-independent and must match across translations. Slugs may
differ. The application uses `guideId` to switch languages safely; if a target
translation is missing or unpublished, it opens that locale's Academy index.

### 4. Push changes

```bash
git add .
git commit -m "Add: your-post-slug"
git push
```

Content will appear on the site within **60 seconds**.

## Guidelines

- Keep Turkish and English terminology aligned with the Academy coverage matrix
- Keep titles under 60 characters
- Keep descriptions between 140-155 characters
- Use proper heading hierarchy (H2 → H3)
- Include relevant internal links
- Add images to improve engagement

## Need Help?

See the full [Blog Writer Guide](https://github.com/serdarildercaglar/youtube-channel-analyzer/blob/production/docs/BLOG_WRITER_PROMPT.md) for SEO best practices and content guidelines.

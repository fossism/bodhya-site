# New Content Command

Create new blog posts or pages with proper formatting and frontmatter.

## Usage
When you run this command, provide:
1. Content type: "blog post" or "page"
2. Title: The page/post title
3. Description: Brief description (used in meta tags)
4. Content: The markdown content
5. Tags: Optional tags for blog posts (comma-separated)

## Template Structure
### For Blog Posts
File location: `content/blog/[slug].md`

```toml
+++
title = "Post Title"
description = "Brief description for social sharing"
date = 2026-03-13
tags = ["tag1", "tag2"]
+++

# Post Title

Your markdown content here...
```

### For Pages
File location: `content/[slug].md`

```toml
+++
title = "Page Title"
description = "Brief description"
+++

# Page Title

Your markdown content here...
```

## Guidelines
- Use lowercase slugs with hyphens (e.g., `my-awesome-post`)
- Descriptions should be under 160 characters
- Use proper markdown formatting (`# h1`, `## h2`, etc.)
- Include at least one section with meaningful content
- For blog posts, always include at least one tag

## After Creation
1. Verify the file was created in the correct location
2. Run `/build-check` to ensure it compiles
3. Run `/visual-check` to see how it looks

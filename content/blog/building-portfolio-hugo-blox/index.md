---
title: "Building My AI/ML Portfolio with Hugo Blox"
date: 2026-01-13
summary: "How I built and customized my developer portfolio using Hugo Blox, featuring AI/ML projects, personalized content, and automated deployment on GitHub Pages"
tags:
  - Hugo
  - Portfolio
  - Static Site
  - GitHub Pages
  - Web Development
authors:
  - me
featured: true
---

As an AI/ML researcher and developer, having a professional portfolio to showcase my projects has been essential. After exploring various options, I chose Hugo Blox (formerly known as Wowchemy/Hugo Academic) to build my portfolio site. Here's my journey and what I learned.

## Why Hugo Blox?

I evaluated several portfolio solutions before settling on Hugo Blox:

- **Speed**: Hugo generates static sites incredibly fast - my entire portfolio builds in under 2 seconds
- **Markdown-first**: All content is in Markdown/YAML, making it easy to version control and AI-friendly
- **Academic/Research Focus**: Built-in support for projects, publications, and technical content
- **Customizable**: Modular block-based system lets me reorder sections without touching templates
- **Free Hosting**: GitHub Pages integration with automatic deployment

Most importantly, it doesn't require maintaining a complex React/Node.js application - just content files and configuration.

## Initial Setup

Getting started was straightforward using the Hugo Blox CLI:

```bash
# Install Hugo Blox CLI globally
npm install -g hugoblox@latest

# Create new site from developer portfolio template
hugoblox create site --template dev-portfolio
```

The template came with a complete structure:
- Pre-configured homepage sections (hero, projects, tech stack, experience)
- Example content showing the expected format
- Netlify and GitHub Pages deployment configs
- Dark mode by default with light mode support

## Customizing for AI/ML Focus

The template was designed for general developers, so I personalized it for my AI/ML specialization:

### 1. Profile Configuration

Updated `data/authors/me.yaml` with my information:

```yaml
name:
  display: Kalidasan Nediyamparambath
role: AI/ML Research Assistant specializing in LLMs & RAG
bio: |
  I'm an Information Technology graduate student focused on 
  LLM-based systems, DevOps automation, and Azure cloud environments.

interests:
  - Large Language Models
  - Retrieval-Augmented Generation
  - DevOps & Automation
  - Cloud Architecture (Azure)
```

### 2. Homepage Sections

The homepage (`content/_index.md`) uses a block-based system. I customized the hero section's typewriter effect:

```yaml
typewriter:
  strings:
    - "LLM-based AI systems"
    - "RAG pipelines"
    - "production ML workflows"
    - "scalable cloud solutions"
  speed: 80
```

### 3. Tech Stack Grid

Updated the tech stack section to reflect my actual tools:

**AI/ML**: PyTorch, Transformers, LangChain, LlamaIndex, Ollama  
**Languages**: Python, SQL, Bash  
**DevOps**: Docker, Git, CI/CD, Azure DevOps  
**Cloud**: Azure (Functions, ML, Storage)

### 4. Project Pages

Each project lives in its own directory with an `index.md` file. For example, my QLORAX project:

```markdown
---
title: 'QLORAX: Production QLoRA Fine-Tuning Suite'
summary: 'MLOps project for production-grade LLM fine-tuning'
tags:
  - AI/ML
  - LLM
  - QLoRA
date: '2024-12-01'
external_link: 'https://github.com/kalidasan-2001/QLORAX'
---

Content with features, technical details, code examples...
```

## Adding Visual Appeal

The template projects had cover images, but mine didn't initially. I created gradient images programmatically using Python PIL:

```python
from PIL import Image, ImageDraw

# Create 1200x630 gradient with project title
img = Image.new('RGB', (1200, 630))
draw = ImageDraw.Draw(img)
# ... gradient and text rendering ...
img.save('content/projects/qlorax/featured.png')
```

Hugo Blox automatically picks up `featured.png` files in project directories and displays them in the portfolio grid.

## Deployment Workflow

GitHub Pages deployment is seamless with the included workflow:

1. Push changes to `main` branch
2. GitHub Actions automatically runs:
   - Installs Hugo and dependencies
   - Builds the site
   - Deploys to `gh-pages` branch
3. Site goes live at `https://username.github.io`

The entire process takes 2-3 minutes from push to live.

## Configuration Tweaks

Key configuration files I modified:

**config/_default/hugo.yaml**:
```yaml
baseURL: 'https://kalidasan-2001.github.io/'
```

**config/_default/params.yaml**:
```yaml
site:
  name: Kalidasan Nediyamparambath
  tagline: AI/ML Research Assistant specializing in LLMs & RAG
  description: Portfolio showcasing AI/ML research projects...
```

## Lessons Learned

### What Worked Well

- **Markdown workflow**: Writing content in Markdown is fast and familiar
- **Version control**: Everything in Git makes it easy to track changes
- **Hugo's speed**: Instant local previews with `hugo server`
- **Block system**: Easy to reorder homepage sections by changing YAML order
- **No build dependencies**: Static output means no server maintenance

### Challenges

- **YAML syntax**: Indentation matters - had to be careful with nested structures
- **Image formats**: Learning the difference between `featured.png` (portfolio grid) vs images in frontmatter
- **Theme customization**: Some design tweaks required understanding Hugo's template hierarchy
- **Documentation navigation**: Hugo Blox docs are comprehensive but took time to find specific features

### Tips for Others

1. **Start with the template**: Don't build from scratch - customize incrementally
2. **Use the dev server**: `hugo server` with live reload is essential
3. **Version control from day one**: Git makes it easy to experiment and revert
4. **Keep content separate**: Don't modify theme files - use params and content files
5. **Test locally before pushing**: `hugo` command to build and check for errors

## What's Next

Future improvements I'm planning:

- **Blog posts on AI/ML topics**: Share learnings from my research projects
- **Publication section**: Add academic papers when published
- **Custom domain**: Currently using GitHub Pages URL, but may add custom domain
- **Analytics**: Add privacy-friendly analytics to track visitors
- **Performance optimization**: Already fast, but could optimize images further

## Conclusion

Hugo Blox struck the perfect balance for my needs - professional appearance, easy content management, and zero hosting costs. The static site approach means excellent performance and security without the complexity of a dynamic application.

For researchers and developers looking to showcase technical work, I highly recommend this approach. The initial setup took about an hour, and customization to match my personal brand took another 2-3 hours. Well worth the investment.

## Resources

- **Live Portfolio**: [kalidasan-2001.github.io](https://kalidasan-2001.github.io)
- **Hugo Blox**: [hugoblox.com](https://hugoblox.com)
- **My GitHub**: [@kalidasan-2001](https://github.com/kalidasan-2001)
- **Hugo Docs**: [gohugo.io/documentation](https://gohugo.io/documentation/)

---

*Have questions about setting up your own portfolio? Feel free to reach out on [LinkedIn](https://www.linkedin.com/in/kalidasan-nediyamparambath-40b46b218/) or check out my repository for reference.*

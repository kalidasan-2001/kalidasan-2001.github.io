---
# Leave the homepage title empty to use the site title
title: ''
summary: ''
date: 2026-01-05
type: landing

design:
  # Default section spacing
  spacing: '0'

sections:
  # Developer Hero - Gradient background with name, role, social, and CTAs
  - block: dev-hero
    id: hero
    content:
      username: me
      greeting: "Hi, I'm"
      show_status: true
      show_scroll_indicator: true
      typewriter:
        enable: true
        prefix: "I build"
        strings:
          - "LLM-based AI systems"
          - "RAG pipelines"
          - "scalable ML workflows"
          - "DevOps automation"
        type_speed: 70
        delete_speed: 40
        pause_time: 2500
      cta_buttons:
        - text: View My Work
          url: "#projects"
          icon: arrow-down
        - text: Get In Touch
          url: "#contact"
          icon: envelope
    design:
      style: centered
      avatar_shape: circle
      animations: true
      background:
        color:
          light: "#fafafa"
          dark: "#0a0a0f"
      spacing:
        padding: ["6rem", "0", "4rem", "0"]
  
  # Filterable Portfolio - Alpine.js powered project filtering
  - block: portfolio
    id: projects
    content:
      title: "Featured Projects"
      subtitle: "A selection of my recent work"
      count: 6
      filters:
        folders:
          - projects
      buttons:
        - name: All
          tag: '*'
        - name: AI/ML
          tag: AI/ML
        - name: DevOps
          tag: DevOps
        - name: Web Dev
          tag: Web Dev
      default_button_index: 0
    design:
      columns: 3
      background:
        color:
          light: "#ffffff"
          dark: "#0d0d12"
      spacing:
        padding: ["4rem", "0", "4rem", "0"]
  
  # Visual Tech Stack - Icons organized by category
  - block: tech-stack
    id: skills
    content:
      title: "Tech Stack"
      subtitle: "Technologies I use to build AI systems"
      categories:
        - name: AI/ML
          items:
            - name: Python
              icon: devicon/python
            - name: TensorFlow
              icon: devicon/tensorflow
            - name: PyTorch
              icon: devicon/pytorch
            - name: LangChain
              icon: academic/book-open
        - name: DevOps & Cloud
          items:
            - name: Docker
              icon: devicon/docker
            - name: Azure
              icon: devicon/azure
            - name: GitHub Actions
              icon: brands/github
            - name: Terraform
              icon: devicon/terraform
        - name: Development
          items:
            - name: Django
              icon: devicon/django
            - name: Java
              icon: devicon/java
            - name: C#
              icon: devicon/csharp
            - name: REST APIs
              icon: academic/code
        - name: Tools
          items:
            - name: Git
              icon: devicon/git
            - name: VS Code
              icon: devicon/vscode
            - name: Linux
              icon: devicon/linux
            - name: PostgreSQL
              icon: devicon/postgresql
    design:
      style: grid
      show_levels: false
      background:
        color:
          light: "#f5f5f5"
          dark: "#08080c"
      spacing:
        padding: ["4rem", "0", "4rem", "0"]
  
  # Experience Timeline
  - block: resume-experience
    id: experience
    content:
      title: Experience
      date_format: Jan 2006
      items:
        - title: Research Assistant
          company: inIT – Institute for Industrial Information Technology
          company_url: 'https://www.init-owl.de'
          company_logo: ''
          location: Lemgo, Germany
          date_start: '2025-11-01'
          date_end: ''
          description: |2-
            * Developed LLM-based conversational assistant for Parkinson's PD Assistant App
            * Implemented RAG pipeline with preprocessing, embeddings, vector search, and context-aware retrieval
            * Designed modular Python scripts for scalable, maintainable LLM workflows
            * Research on hallucination reduction, evaluation metrics, and safety alignment
            * Tech stack: Python, LLMs, RAG, Vector Databases, Prompt Engineering
        - title: Virtual Intern – Machine Learning, AI & Deep Learning
          company: Remote
          company_url: ''
          company_logo: ''
          location: Remote
          date_start: '2022-11-01'
          date_end: '2023-02-28'
          description: |2-
            * Built and trained CNN, ANN, and supervised models using Python and TensorFlow
            * Developed automation-oriented ML projects with data preprocessing and training workflows
            * Gained foundational understanding of AI-driven automation and computer vision pipelines
            * Tech stack: Python, TensorFlow, CNN, ANN, Computer Vision
    design:
      columns: '1'
      background:
        color:
          light: "#ffffff"
          dark: "#0d0d12"
      spacing:
        padding: ["4rem", "0", "4rem", "0"]
  
  # Recent Blog Posts
  - block: collection
    id: blog
    content:
      title: Recent Posts
      subtitle: 'Thoughts on AI, ML, and tech'
      text: ''
      filters:
        folders:
          - blog
        exclude_featured: false
      count: 3
      order: desc
    design:
      view: card
      columns: 3
      background:
        color:
          light: "#f5f5f5"
          dark: "#08080c"
      spacing:
        padding: ["4rem", "0", "4rem", "0"]
  
  # Contact Section
  - block: contact-info
    id: contact
    content:
      title: Get In Touch
      subtitle: "Let's collaborate on AI/ML projects"
      text: |-
        I'm always interested in hearing about new research opportunities and student positions.
        Whether you're looking to collaborate, hire, or just want to connect, feel free to reach out!
      email: kalidasann2001@gmail.com
      autolink: true
    design:
      columns: '1'
      background:
        color:
          light: "#ffffff"
          dark: "#0d0d12"
      spacing:
        padding: ["4rem", "0", "4rem", "0"]
  
  # CTA Card
  - block: cta-card
    content:
      title: "Open to Student Roles & Research Opportunities"
      text: |-
        I'm actively seeking **student assistant positions**, **research opportunities**, and **internships** in AI/ML and DevOps.
        
        Let's connect and discuss how I can contribute to your team.
      button:
        text: 'View GitHub'
        url: https://github.com/kalidasan-2001
        new_tab: true
    design:
      card:
        css_class: 'bg-gradient-to-br from-primary-200 via-primary-100 to-secondary-200 dark:from-primary-600 dark:via-primary-700 dark:to-secondary-700'
        text_color: dark
      background:
        color:
          light: "#f5f5f5"
          dark: "#08080c"
      spacing:
        padding: ["4rem", "0", "6rem", "0"]
---

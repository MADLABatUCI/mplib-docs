---
title: 'MPLib.js'
date: 2023-10-24
type: landing

design:
  # Default section spacing
  spacing: "6rem"

sections:
  - block: hero
    content:
      title: MPLib.js Documentation
      text: A MultiPlayer Gaming Library for Researchers! 🎮
      primary_action:
        text: Get Started
        url: /mplib-docs/tutorial/
        icon: rocket-launch
      secondary_action:
        text: Read the docs
        url: /mplib-docs/docs/
      announcement:
        text: "Learn how to create your own research game."
        link:
          text: "Tutorial"
          url: "/mplib-docs/tutorial/"
    design:
      spacing:
        padding: [0, 0, 0, 0]
        margin: [0, 0, 0, 0]
      # For full-screen, add `min-h-screen` below
      css_class: ""
      background:
        color: ""
        image:
          # Add your image background to `assets/media/`.
          filename: ""
          filters:
            brightness: 0.5
  - block: stats
    content:
      items:
        - statistic: "5+"
          description: |
            Game Demos
        - statistic: "Serverless"
          description: |
            Run experiments without a server
        - statistic: "10+"
          description: |
            Live experiments use this library
    design:
      # Section background color (CSS class)
      css_class: "bg-gray-400 dark:bg-gray-800"
      # Reduce spacing
      spacing:
        padding: ["1rem", 0, "1rem", 0]
  - block: features
    id: features
    content:
      title: Features
      text: Collaborate, publish, and maintain technical knowledge with an all-in-one documentation site. Used by 100,000+ startups, enterprises, and researchers.
      items:
        - name: Optimized SEO
          icon: magnifying-glass
          description: Automatic sitemaps, RSS feeds, and rich metadata take the pain out of SEO and syndication.
        - name: Fast
          icon: bolt
          description: Super fast page load with Tailwind CSS and super fast site building with Hugo.
        - name: Easy
          icon: sparkles
          description: One-click deployment to GitHub Pages. Have your new website live within 5 minutes!
        - name: No-Code
          icon: code-bracket
          description: Edit and design your site just using rich text (Markdown) and configurable YAML parameters.
        - name: Highly Rated
          icon: star
          description: Rated 5-stars by the community.
        - name: Swappable Blocks
          icon: rectangle-group
          description: Build your pages with blocks - no coding required!
  - block: cta-card
    content:
      title: "Start Creating Your Own <u>Serverless</u> Multiplayer Experiment"
      text: MPLib.js facilitates the process of creating multiplayer online experiments.<br />Easily create new experiments with minimal programming experience!
      button:
        text: Walkthrough Tutorial
        url: /mplib-docs/tutorial/
    design:
      card:
        # Card background color (CSS class)
        css_class: "bg-primary-700"
        css_style: ""
---

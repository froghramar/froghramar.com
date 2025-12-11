---
layout: post
title:  "Why I Built a JSON-Based Resume Generator"
date:   2025-12-11 21:35:17 +0600
categories: pet-projects
image:
    path: /assets/images/json-resume-generator.png
tags:
    - automation
---

# Why I Built a JSON-Based Resume Generator (And Why You Should Too)

Over the years, I've updated my resume dozens of times. Each update meant opening a Word document, adjusting formatting, ensuring consistency across sections, and then converting to PDF. It was tedious, error-prone, and frankly, not how a developer should manage structured data.

So I built something better: a JSON-based resume generator that separates content from presentation, validates data automatically, and outputs beautiful HTML and PDF versions with a single command.

## The Problem with Traditional Resume Management

Most professionals maintain their resumes in word processors, which creates several challenges:

- **Version control nightmares**: Multiple files scattered across different folders, each representing a slightly different version
- **Format inconsistencies**: Manual formatting leads to misaligned dates, inconsistent spacing, and styling errors
- **Content duplication**: Maintaining separate versions for different purposes means updating information in multiple places
- **No data validation**: Nothing prevents you from adding incomplete information or making formatting mistakes

## The Solution: Treat Your Resume as Data

My approach treats resume content as structured data stored in JSON format. This might sound technical, but the benefits are substantial:

**Content as Code**: Your resume becomes a single source of truth. All information lives in one JSON file that's easy to edit, version control with Git, and validate against a schema.

**Automated Generation**: A Python script reads the JSON, validates it against a schema, and generates both HTML and PDF versions using a customizable Jinja2 template. No manual formatting required.

**CI/CD Pipeline**: GitHub Actions automatically builds and deploys your resume whenever you push changes. The latest version is always available at a clean URL through GitHub Pages.

## What Makes This Approach Special

The system I built includes several thoughtful features:

**Schema Validation**: A JSON schema ensures your resume data is always complete and correctly formatted. Missing required fields? The validator catches it before generation.

**Flexible Experience Tracking**: Support for both single roles and grouped positions at the same company, with automatic duration calculations that intelligently display years and months.

**Professional Presentation**: The template includes modern typography, responsive layout, and properly formatted PDF output with page numbers and optimized spacing.

**Easy Customization**: Want to change the layout or add new sections? Simply edit the HTML template. All the data binding is handled through Jinja2 macros.

## Real-World Benefits

Since implementing this system, I've experienced several practical advantages:

1. **Updating is effortless**: Adding a new position or certification takes 30 seconds of JSON editing, not 30 minutes of formatting
2. **Version history is transparent**: Git shows exactly what changed and when
3. **Multiple formats are free**: Generate web, PDF, or any other format from the same source data
4. **Consistency is guaranteed**: Schema validation prevents incomplete or incorrectly formatted entries

## Beyond Personal Use

While I built this for my own resume, the approach has broader applications. Teams could use similar systems for:

- Company bios and employee profiles
- Project portfolios
- Case study documentation
- Any content that requires consistent formatting and frequent updates

## Technical Highlights

For those interested in the implementation:

- **Python** with jsonschema for validation
- **Jinja2** templating engine for flexible HTML generation
- **WeasyPrint** for high-quality PDF rendering
- **GitHub Actions** for automated builds and deployment
- **GitHub Pages** for hosting the live resume

The entire codebase is open source and available on GitHub, serving both as a functional tool and a reference implementation for similar projects.

## Final Thoughts

This project represents a philosophy I try to apply across my work: when you encounter a repetitive, manual process, ask yourself if there's a way to automate it properly. Not just quick scripts or shortcuts, but thoughtful systems that solve the underlying problem.

Your resume is important. It deserves better than manual formatting in a word processor. Treat it like the structured data it is, and you'll save time while improving quality.

---

**Check out the project**: https://github.com/froghramar/resume  
**See the live demo**: https://feroz.dev/resume

Have you automated any traditionally manual processes in your work? I'd love to hear about your approaches in the comments.

#SoftwareDevelopment #Automation #CareerDevelopment #OpenSource #Python
# Personal Website

This repository hosts my personal branding website, showcasing my professional journey, projects, and expertise in AWS and cybersecurity.

## 🌐 Website Overview

My personal website serves as a centralized hub for:
- Professional background and experience
- Technical blog posts about AWS and cybersecurity
- Project portfolio
- Professional resume
- Contact information

## 🛠 Technical Stack

This website is built with:
- [Jekyll](https://jekyllrb.com/) - Static site generator
- GitHub Pages - Hosting platform
- [Indigo Theme](https://github.com/sergiokopplin/indigo) - Base theme with customizations
- Custom CSS/HTML modifications for personal branding

## 🚀 Features

- Responsive design for all devices
- Dark/Light theme support
- Blog section for technical content
- Integrated resume viewer
- Project showcase
- Social media integration
- RSS feed for blog posts

## 📝 Content Updates

### Adding New Blog Posts
1. Create a new markdown file in `_posts` directory
2. Use the format: `YYYY-MM-DD-title.md`
3. Include required front matter:
   ```yaml
   ---
   title: "Your Post Title"
   layout: post
   date: YYYY-MM-DD HH:MM
   tag: [tag1, tag2]
   category: category
   ---
   ```

### Updating Resume
1. Replace the PDF file in `assets/resume.pdf`
2. The changes will automatically reflect on the resume page

## 💻 Local Development

To run this website locally:

1. Install prerequisites:
   ```bash
   gem install bundler jekyll
   ```

2. Clone the repository:
   ```bash
   git clone https://github.com/GioAwsDev/GioAwsDev.github.io.git
   cd GioAwsDev.github.io
   ```

3. Install dependencies and run:
   ```bash
   bundle install
   bundle exec jekyll serve
   ```

4. Visit `http://localhost:4000` in your browser



## 📄 License

This website is built on the Indigo theme, which is licensed under the [MIT License](https://kopplin.mit-license.org/) © Sérgio Kopplin.
Content and personal modifications © 2025 Giovannie Encarnacion.

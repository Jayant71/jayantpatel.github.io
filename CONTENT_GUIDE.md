# Content Management Guide

Welcome to your Research Portfolio! This website is built with Astro and is designed to be very easy to update.

All the text and data for your portfolio is stored in simple JSON files inside the `src/data/` folder. 

## How to Edit Content

### 1. Profile Data (`src/data/profile.json`)
This file controls the Hero section at the top of your homepage.
- **name**: Your name.
- **image**: URL to your profile picture.
- **tagline**: The large text below your name.
- **bioHtml**: Your biography. You can use simple HTML tags like `<strong>text</strong>` or `<a>links</a>` here.
- **resumeUrl**: The link for the "CV / Resume" button.
- **links**: The social media/contact badges under your photo.

### 2. News (`src/data/news.json`)
This file controls the "Latest News" section. It's a list of events.
- To add a new news item, add a new block at the top of the list in this format:
```json
{
  "date": "MONTH YEAR",
  "content": "Your news text. You can use <strong>bold</strong> or <a href='link'>links</a>."
}
```

### 3. Publications (`src/data/publications.json`)
This file controls the "Selected Publications" section on the homepage.
- **id**: A unique identifier for the publication. This is very important as it determines the URL for the detailed research page (e.g., `/research/my-publication-id`).
- **title**: The paper title.
- **authors**: The author list. 
- **venue**: The conference or journal name.
- **image**: The thumbnail image for the publication.
- **badge**: (Optional) e.g., "Oral Presentation" or "Best Paper".
- **links**: Add buttons for PDF, Code, Dataset, Demo. The accepted icons are `file-text`, `code`, `database`, `play`.

### 4. Detailed Research Pages (`src/data/projects.json`)
This file controls the individual pages for your research projects (the ones linked from the publications section).
- **slug**: Must exactly match the `id` you used in `publications.json`.
- **title, authors, affiliation**: Header information.
- **abstract**: The abstract text.
- **methodology**: A list of bullet points explaining your method.
- **resultsTable**: The data for the quantitative results table.
  - **headers**: The column names.
  - **rows**: The data rows (must have the same number of items as headers).
- **links**: Buttons at the bottom of the page.

### Modifying Styles
If you want to change colors or fonts, you can edit the CSS variables in `src/styles/global.css`:
- `--color-primary`: The main accent color (default is blue).
- `--color-text`: Main text color.
- `--color-bg`: Main background color.

# AI Content Repurposing Automation

An AI-powered content repurposing workflow built with **n8n** and **Google Gemini**. It transforms a blog article into **21 ready-to-edit content variations** across seven social media formats and three distinct tones, then delivers the generated content through Gmail.

## Overview

Creating platform-specific content from a single article can be repetitive and time-consuming. This workflow automates the process: submit a blog URL, extract the article text, generate tailored content with an AI agent, and receive the results in a formatted email.

## Key Features

- **Blog URL input** through an n8n form trigger.
- **Automatic webpage extraction** using an HTTP Request node and HTML extraction.
- **AI-powered content generation** using Google Gemini through the n8n AI Agent.
- **Seven content formats**, each generated in three tones:
  - LinkedIn Post
  - Instagram Caption
  - Instagram Post Idea
  - Instagram Reel Idea
  - Instagram Reel Script
  - Twitter/X Thread
  - WhatsApp Message
- **Three tone variations:** Professional, Friendly, and Persuasive.
- **Formatted Gmail delivery** of the generated content.

## Workflow

```text
Blog URL Submission
        |
        v
   HTTP Request
        |
        v
  HTML Extraction
        |
        v
     AI Agent
  (Google Gemini)
        |
        v
  21 Content Variations
        |
        v
   Gmail Delivery
```

## Technologies Used

- **n8n** — workflow automation
- **Google Gemini** — AI-powered content generation
- **HTTP Request** — webpage retrieval
- **HTML Extract** — article text extraction
- **Gmail** — email delivery

## How It Works

1. Submit a publicly accessible blog article URL through the workflow form.
2. The HTTP Request node retrieves the webpage.
3. The HTML node extracts the page's body text for processing.
4. The AI Agent uses Google Gemini to create seven content formats in three tones.
5. The generated HTML-formatted content is sent to the configured Gmail address.

## Workflow Export

The sanitized n8n workflow JSON is available here:

**[Download the n8n workflow JSON](workflow/content-repurposing-workflow.json)**

To use it:

1. Download the JSON file.
2. In n8n, import the workflow from the downloaded JSON file.
3. Configure your own Google Gemini and Gmail credentials in the relevant nodes.
4. Replace `YOUR_EMAIL_ADDRESS` in the Gmail node with your preferred recipient address.
5. Review the workflow settings, test it with a blog URL, and activate it when ready.

> **Security:** The shared export does not contain the original account credential references or personal recipient email. Never commit API keys, access tokens, passwords, OAuth secrets, or private webhook URLs.

## Scope and Limitations

- The source webpage must be publicly accessible and contain extractable text.
- Generated content should be reviewed for accuracy and adapted before publishing.
- WhatsApp messages are generated as one of the content formats; automated WhatsApp delivery is not configured in the current version.

## Future Improvements

- Add an optional WhatsApp Business Platform integration.
- Support additional content platforms and output formats.
- Add improved handling for webpages with complex layouts.
- Include options to customize tone, audience, and content length.

## Project Status

**Version:** 1.1  
**Status:** Core workflow implemented and successfully tested with Gmail delivery. Sanitized n8n workflow export included.

---

*Built with n8n and Google Gemini.*

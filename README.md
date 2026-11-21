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

## Setup

1. Create an n8n account and open a new workflow.
2. Import the workflow export if one is provided in this repository, or recreate the nodes following the workflow diagram above.
3. Configure the form trigger, HTTP Request, HTML extraction, AI Agent, and Gmail nodes.
4. Connect your own Google Gemini and Gmail credentials through n8n's credential manager.
5. Activate or publish the workflow and submit a blog URL to test it.

> **Note:** This repository documents the project. The n8n workflow export should be added separately after removing credentials, tokens, and other private information. Never commit API keys, access tokens, passwords, or personal credentials.

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

**Version:** 1.0  
**Status:** Core workflow implemented and successfully tested with Gmail delivery.

---

*Built with n8n and Google Gemini.*

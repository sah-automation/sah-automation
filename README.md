# Sonu Gupta

Automation Engineer | AI Workflows | Python | n8n

I build automation systems that help businesses scale operations using AI, APIs, and workflow automation.

## Core Skills

• Workflow Automation (n8n)\
• Python Automation Scripts\
• AI API Integrations\
• Web Scraping & Data Pipelines\
• Ecommerce Automation\
• Lead Generation Systems

## Featured Projects

### WooCommerce Inventory Management Automation
An end-to-end automation solution built with n8n to streamline inventory management between WooCommerce and Google Sheets.
[WooCommerce Inventory Management Automation](https://github.com/sah-automation/woocommerce-inventory-management-automation)
```mermaid
graph TD
    subgraph External_Triggers [External Triggers]
        WC[WooCommerce Webhook]
        CRON[Daily 8AM Schedule]
        Tally[Tally Restock Form]
        Approve[Manual Approval Webhook]
    end

    subgraph n8n_Logic [n8n Orchestration]
        Deduct[Stock Deduction Logic]
        Monitor[Low Stock Monitoring]
        Restock[Restock Processing]
        Error[Global Error Handler]
    end

    subgraph Storage [Storage / Database]
        GS_Inv[(Google Sheets: Inventory)]
        GS_Log[(Google Sheets: Order Logs)]
        GS_Err[(Google Sheets: Error Logs)]
    end

    subgraph Notifications [Notifications & Comms]
        Gmail[Gmail: Admin/Suppliers]
        Slack[Slack: Team Alerts]
    end

    WC --> Deduct
    Deduct --> GS_Inv
    Deduct --> GS_Log
    
    CRON --> Monitor
    Monitor --> GS_Inv
    Monitor --> Gmail

    Tally --> Restock
    Restock --> GS_Inv
    Restock --> Slack
    Restock --> Gmail

    Approve --> Restock
    
    n8n_Logic -.-> Error
    Error --> GS_Err
    Error --> Gmail
    Error --> Slack
```

### Email Marketing Automation
N8N workflows designed to automate a multi-step cold email outreach campaign. It uses Google Sheets as a central tracking system and Gmail for deliverability.
[Email Outreach Automation with n8n](https://github.com/sah-automation/email-marketing-automation-n8n)

### AI Wordpress Blog Automation
An advanced n8n workflow that automates the entire content lifecycle: from SEO-driven research and planning to professional writing, styled HTML formatting, and WordPress publishing.
[WordPress Auto-Blogging with n8n](https://github.com/sah-automation/wordpress-auto-blogger)

### Woocommerce Product Automation System
Large scale automation system that scrapes supplier product data, optimizes with AI, and publishes to WooCommerce using REST API. This system streamlines the process of extracting complex product details, including variations, attributes, and high-quality images.
[Woocommerce Product Lister](https://github.com/sah-automation/woocommerce-product-lister)
```mermaid
graph TD
    A[Supplier Website] -->|Browser Automation| B(Automa Scraper)
    B -->|Structured Extraction| C[data/LuxeDecor2Woo-listing-data.csv]
    C -->|Input| D(Google Colab Notebook / Python)
    D -->|WooCommerce REST API| E[WooCommerce Store]
    
    subgraph "Data Extraction Layer"
    B
    end
    
    subgraph "Data Storage"
    C
    end
    
    subgraph "Integration Layer"
    D
    E
    end
```

### Google Maps Lead Generation Automation
An automated, end-to-end lead generation pipeline built on n8n. It intelligently sources business leads from Google Maps, conducts deep prospect research using Google Gemini, and verifies email deliverability via the Reoon API.
[AI-Powered Lead Generation Engine](https://github.com/sah-automation/b2b-lead-generation)
```mermaid
graph TD
    A[Trigger] --> B[Step 1: Lead Sourcing]
    B --> C[Step 2: Data Structuring]
    C --> D[Step 3: AI Prospect Research]
    D --> E[Step 4: Email Verification]
    E --> F[Final Outreach Data]
```

### Ecommerce AI Voice Assistant
An advanced AI-powered voice assistant designed for ecommerce store. This system leverages Vapi for high-fidelity voice interactions and n8n for robust backend automation, integrating directly with WooCommerce and multiple AI models.
[Ecommerce AI Voice Assistant](https://github.com/sah-automation/ecommerce-AI-voice-assistant)
```mermaid
graph TD
    User((User)) <--> Vapi[Vapi Voice AI]
    Vapi -- Webhook (Tool Call) --> n8n[n8n Automation Engine]
    
    subgraph n8n Workflows
        n8n --> Woo[WooCommerce API]
        n8n --> Perp[Perplexity AI / Search]
        n8n --> Gemini[Google Gemini / LLM]
        n8n --> SMTP[SMTP / Email]
    end
    
    Woo <--> DB[(WooCommerce Store)]
    Perp <--> Web((Internet))
```

## Tech Stack

Python\
n8n\
REST APIs\
Web Scraping\
AI APIs\
WordPress / WooCommerce

## Open to

Automation Engineer roles\
AI Automation Specialist roles\
Workflow Automation roles

## Workflow Overview

![automa-product-scraper](screenshots/automa-product-scraper.png)
![email-opt-out](screenshots/email-opt-out.png)
![first-email-workflow](screenshots/first-email-workflow.png)
![first-follow-up-email-workflow](screenshots/first-follow-up-email-workflow.png)
![second-follow-up-email-workflow](screenshots/second-follow-up-email-workflow.png)
![vapi-call-start-end-tool](screenshots/vapi-call-start-end-tool.png)
![vapi-get-order-tool](screenshots/vapi-get-order-tool.png)
![vapi-get-product-tool](screenshots/vapi-get-product-tool.png)
![wordpress-auto-blog-posting-n8n-workflow](screenshots/wordpress-auto-blog-posting-n8n-workflow.png)
![workflow-screenshot](screenshots/workflow-screenshot.png)

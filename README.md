Teletext News Browser

A secure, text-only news reader that mimics a classic teletext/notepad interface. It uses the Gemini API with Google Search Grounding to fetch and summarize real-time news headlines from BBC UK, ABC Australia, and BBC Australia.

Features

Real-Time News: Fetches live headlines using AI-driven search queries.

Text-Only Mode: Reads full stories in a clean, unformatted plain-text view.

Secure Architecture: Uses a Cloudflare Worker proxy to hide the API key.

Teletext/Notepad UI: Minimalist design with system fonts and no clutter.

Configurable: Uses a config.json file for easy setup without touching the code.

Architecture

This project uses a hybrid architecture to host the site for free while keeping credentials secure:

Frontend (GitHub Pages):

index.html: The main application logic.

style.css: The visual styling.

config.json: Stores your API endpoint URL.

Backend (Cloudflare Workers):

gemini-proxy.js: A serverless function that securely holds your Google Gemini API key and handles requests from the frontend.

Setup Guide

Part 1: The Backend (Cloudflare)

Create a free account at Cloudflare Workers.

Create a new Worker (e.g., named news-proxy).

Click Edit Code and paste the contents of gemini-proxy.js. Save and Deploy.

Go to Settings -> Variables in your Worker dashboard.

Add a variable named GEMINI_API_KEY and paste your Google Gemini API key as the value. Encrypt and Save.

Copy your Worker's URL (e.g., https://news-proxy.your-name.workers.dev).

Part 2: The Frontend (GitHub)

Create a new repository on GitHub.

Upload the following files:

index.html

style.css

Create a file named config.json with the following content (replace with your actual Worker URL):

{
    "proxyApiUrl": "[https://news-proxy.your-name.workers.dev](https://news-proxy.your-name.workers.dev)"
}


Go to Settings -> Pages in your GitHub repository and enable GitHub Pages (Select main branch as source).

Part 3: Usage

Visit your GitHub Pages URL. The app will load, fetch the proxy URL from config.json, and immediately start retrieving the latest headlines.

Click a tab to switch news regions.

Click a headline to read the full AI-summarized story.

Click "Refresh Headlines" to get the latest update.

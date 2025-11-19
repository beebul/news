Teletext News Browser
=====================

A secure, text-only news reader that mimics a classic teletext/notepad interface. It uses the **Gemini API** with **Google Search Grounding** to fetch and summarize real-time news headlines from BBC UK, ABC Australia, and BBC Australia.

Features
--------

*   **Real-Time News:** Fetches live headlines using AI-driven search queries.
    
*   **Text-Only Mode:** Reads full stories in a clean, unformatted plain-text view.
    
*   **Secure Architecture:** Uses a Cloudflare Worker proxy to hide the API key.
    
*   **Teletext/Notepad UI:** Minimalist design with system fonts and no clutter.
    
*   **Configurable:** Uses a config.json file for easy setup without touching the code.
    

Architecture
------------

This project uses a **hybrid architecture** to host the site for free while keeping credentials secure:

1.  **Frontend (GitHub Pages):**
    
    *   index.html: The main application logic.
        
    *   style.css: The visual styling.
        
    *   config.json: Stores your API endpoint URL.
        
2.  **Backend (Cloudflare Workers):**
    
    *   gemini-proxy.js: A serverless function that securely holds your Google Gemini API key and handles requests from the frontend.
        

Setup Guide
-----------

### Part 1: The Backend (Cloudflare)

1.  Create a free account at [Cloudflare Workers](https://workers.cloudflare.com/).
    
2.  Create a new Worker (e.g., named news-proxy).
    
3.  Click **Edit Code** and paste the contents of gemini-proxy.js. Save and Deploy.
    
4.  Go to **Settings -> Variables** in your Worker dashboard.
    
5.  Add a variable named GEMINI\_API\_KEY and paste your Google Gemini API key as the value. Encrypt and Save.
    
6.  Copy your Worker's URL (e.g., https://news-proxy.your-name.workers.dev).
    

### Part 2: The Frontend (GitHub)

1.  Create a new repository on GitHub.
    
2.  Upload the following files:
    
    *   index.html
        
    *   style.css
        
3.  { "proxyApiUrl": "\[https://news-proxy.your-name.workers.dev\](https://news-proxy.your-name.workers.dev)"}
    
4.  Go to **Settings -> Pages** in your GitHub repository and enable GitHub Pages (Select main branch as source).
    

### Part 3: Usage

Visit your GitHub Pages URL. The app will load, fetch the proxy URL from config.json, and immediately start retrieving the latest headlines.

*   **Click a tab** to switch news regions.
    
*   **Click a headline** to read the full AI-summarized story.
    
*   **Click "Refresh Headlines"** to get the latest update.

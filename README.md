Text-Only News Browser https://gemini.google.com/app/4eb69f5feeb66f4c?hl=en-AU

This is a simple, single-file web application that acts as a text-only news browser. It uses the Gemini API to provide a clean, terminal-style interface for browsing news headlines and reading full, plain-text summaries of the stories.

How It Works

Headline Generation: The app first calls the Gemini API (without search) to generate a list of 8 plausible, current-sounding headlines for a selected news region (e.g., BBC UK). This ensures a list is always available.

Story Retrieval: When you click a headline, the app performs a new API call using that headline text as a query. This second call does use Google Search grounding to find real-time, relevant news and generate a comprehensive, plain-text summary of the story.

How to Use

Simply open the index.html file in any modern web browser.

How to Host Your App for Free

Because this is a single index.html file (a "static site"), you can host it for free on several platforms.

1. Netlify (Easiest & Fastest)

This is the top recommendation if you just want to get it online right now.

How it works:

Create a free account on Netlify.

On your main dashboard, find the "Netlify Drop" (or "Sites") section.

Drag your index.html file from your computer directly onto that box in your browser.

In seconds, it will be live on a free *.netlify.app URL.

2. GitHub Pages (Most Common for Developers)

This is the standard, free way to host projects if you are using a GitHub repository.

How it works:

Create a new public repository on GitHub.

Upload your index.html and README.md files to that repository.

Go to the repository's "Settings" tab.

On the left-hand menu, click on "Pages".

Under "Build and deployment," select your main (or master) branch as the source.

Click "Save". After a minute or two, your site will be live at a URL like your-username.github.io/your-repository-name.

3. Vercel / Cloudflare Pages


These are two other fantastic, modern platforms that are very similar to Netlify and also offer generous free tiers for static sites.

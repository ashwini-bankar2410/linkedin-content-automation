# linkedin-content-automation
An n8n workflow that reads an article and uses AI to automatically generate and publish a summarized post to LinkedIn.

# LinkedIn Content Automation using n8n
## What it does
Automatically generates and publishes LinkedIn posts using a 
two-stage AI processing pipeline, triggered by updates to a 
Google Sheet.

## Tools used
- n8n (workflow automation)
- Google Sheets (data source & trigger)
- Google Gemini AI (two-stage content generation)
- LinkedIn API (publishing)

## How it works
1. *Trigger:* Workflow starts automatically when a new row/update 
   is added to a Google Sheet
2. *Stage 1 (AI Processing):* A Basic LLM Chain node sends the 
   Sheet data to Google Gemini for initial content generation
3. *Stage 2 (AI Refinement):* A second Basic LLM Chain node 
   further refines the output for a polished, post-ready format
4. *Publish:* The final content is automatically posted to 
   LinkedIn via the LinkedIn API

## Why two AI chains?
Splitting the generation into two stages allows for better 
control — the first stage focuses on understanding/drafting 
content, while the second focuses on refining tone and format 
before publishing.

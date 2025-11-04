# **🧠 AI-Powered Instagram Competitor Strategy Analyst**

This workflow automates deep content and strategy analysis for competitor Instagram accounts. It combines data scraping with a powerful multi-modal AI pipeline (Gemini) to not only tell you what your competitors are posting, but *why* it's working (or not working), and what you should do next.

## **🚀 How It Works (High-Level Flow)**

The process is broken down into four logical stages:

1. **Scrape & Collect:** Downloads recent posts, including media and captions, from specified competitor profiles.  
2. **Deduplicate & Filter:** Checks the Google Sheet database to ensure only genuinely new content that hasn't been analyzed before is processed.  
3. **AI Analysis:** Runs the new content through an advanced AI model (Gemini) to analyze images, videos, and text captions for themes, tone, and visual elements.  
4. **Strategy Generation:** Synthesizes all gathered metrics and AI insights to generate final, actionable content recommendations.

## **🔑 Prerequisites & Required Services**

This workflow relies on the following services for data collection and intelligence:

| Service | Purpose | Requirement |
| :---- | :---- | :---- |
| **Google Sheets** | Database for storing all post data and AI analysis results. | A Google Project having Sheets & Docs APIs enabled |
| **Apify** | Web scraping tool for extracting high-volume Instagram data. | [Apify API Key](https://console.apify.com/settings/integrations) |
| **Gemini / Google AI** | Multi-modal analysis of content (images, video, text) and strategy generation. | Access to [Gemini API](https://aistudio.google.com/app/api-keys) 

## **⚙️ Setup & Configuration**

Set up should take less than 5 minutes. You only need to configure the core inputs:

1. **Install Apify Node**: Ensure you have the community node `@apify/n8n-nodes-apify` installed in your workflow environment to connect to the scraping tool.
2. **Target Accounts:** Provide the list of competitor Instagram usernames you wish to monitor in the initial scraping configuration.
3. **Post Limit:** Set the max\_posts value to specify how many of the latest posts should be pulled per account during each run.  

## **🎯 STEP 1: Content Collection (Scraping)**

This step downloads recent content (posts, videos, and images) from the Instagram competitor accounts you have defined.

<img width="503" height="367" alt="Screenshot 2025-11-04 162301" src="https://github.com/user-attachments/assets/0a8738b9-7e1e-4de2-be24-a9f1be2b8f4b" />

## **🔍 STEP 2: Duplicate Prevention (Filtering)**

To save resources and maintain data quality, this step ensures that the system only processes genuinely new content. It checks the post IDs against the content already logged in your **Google Sheet** and filters out any duplicates before the next stage.

<img width="725" height="378" alt="Screenshot 2025-11-04 162334" src="https://github.com/user-attachments/assets/f6264509-7be9-4956-b2b0-d4db7c18c232" />

## **🧠 STEP 3: Deep Content Analysis (AI Pipeline)**

New content is processed by the Gemini model, which uses multi-modal intelligence to extract meaning from every part of the post:

* **Visual Analysis:** Extracts key elements like persons, objects, themes, and emotional tone from images and video thumbnails.  
* **Text Analysis:** Analyzes the caption and comments for meaning, tone, and sentiment.  
* **Data Storage:** The comprehensive analysis results are saved into the Google Sheet, associated with the unique post ID.

<img width="1253" height="617" alt="Screenshot 2025-11-04 162401" src="https://github.com/user-attachments/assets/483dde62-1a33-4499-8e72-a703171709ed" />

## **📈 STEP 4: Strategy & Recommendation**

The final stage acts as a "Strategy Specialist AI," synthesizing all the gathered data—performance metrics (likes, comments, etc.) and the deep AI analysis—to provide a final report:

* **Key Insights:** Identifies trends, such as the most engaged content themes, the best-performing media types (Reels vs. Images), and viral hashtags.  
* **Actionable Strategy:** Provides specific, personalized recommendations for content experiments based on what is currently succeeding and failing in the competitor landscape.

<img width="645" height="282" alt="Screenshot 2025-11-04 162425" src="https://github.com/user-attachments/assets/604155bc-b15a-45ac-a051-4431ceaa2de4" />

## 🛠️ Customize Your Workflow

While this workflow is built and optimized for the Gemini / Google AI model for multi-modal analysis, the core logic is flexible. You can easily:
- replace the AI nodes in STEP 3 and STEP 4 with a connector for any other AI provider (e.g., OpenAI, Claude) that meets your requirements.
- Fine tune the prompt messages to the format you want.
- Further pass the final insights to other AI workflows that generates content automatically based on the recommendations, & more..

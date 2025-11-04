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

| Service                | Purpose                                                      | Requirement                   |
| :--------------------- | :----------------------------------------------------------- | :---------------------------- |
| **Google Sheets**      | Database for storing all post data and AI analysis results.  | An active Google account.     |
| **Apify**              | Web scraping tool for extracting high-volume Instagram data. | An Apify account and API Key. |
| **Gemini / Google AI** | Multi-modal analysis of content (images, video, text) and strategy generation. | Access to the Gemini API.     |

## **⚙️ Setup & Configuration**

Set up should take less than 5 minutes. You only need to configure the core inputs:

1. **Target Accounts:** Provide the list of competitor Instagram usernames you wish to monitor in the initial scraping configuration.  
2. **Post Limit:** Set the max\_posts value to specify how many of the latest posts should be pulled per account during each run.  
3. **Apify API Key:** Input your API key into the designated connector node.

## **🎯 STEP 1: Content Collection (Scraping)**

This step downloads recent content (posts, videos, and images) from the Instagram competitor accounts you have defined.

## **🔍 STEP 2: Duplicate Prevention (Filtering)**

To save resources and maintain data quality, this step ensures that the system only processes genuinely new content. It checks the post IDs against the content already logged in your **Google Sheet** and filters out any duplicates before the next stage.

## **🧠 STEP 3: Deep Content Analysis (AI Pipeline)**

New content is processed by the Gemini model, which uses multi-modal intelligence to extract meaning from every part of the post:

* **Visual Analysis:** Extracts key elements like persons, objects, themes, and emotional tone from images and video thumbnails.  
* **Text Analysis:** Analyzes the caption and comments for meaning, tone, and sentiment.  
* **Data Storage:** The comprehensive analysis results are saved into the Google Sheet, associated with the unique post ID.

## **📈 STEP 4: Strategy & Recommendation**

The final stage acts as a "Strategy Specialist AI," synthesizing all the gathered data—performance metrics (likes, comments, etc.) and the deep AI analysis—to provide a final report:

* **Key Insights:** Identifies trends, such as the most engaged content themes, the best-performing media types (Reels vs. Images), and viral hashtags.  
* **Actionable Strategy:** Provides specific, personalized recommendations for content experiments based on what is currently succeeding and failing in the competitor landscape.

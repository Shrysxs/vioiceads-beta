+-----------------------+
|         USER          |
|  Business / Marketer  |
+-----------+-----------+
            |
            | Business Details
            | Reviews (Text / CSV)
            v
+-----------------------+
|       FRONTEND        |
|   (React / Next.js)   |
|-----------------------|
| - Business Context    |
| - Reviews Input       |
| - Generate Button     |
+-----------+-----------+
            |
            | POST /generate (JSON)
            v
+-----------------------+
|        BACKEND        |
|    (Node / API)       |
+-----------+-----------+
            |
            | Clean & Normalize Data
            v
+-----------------------+
|   PRE-PROCESS LAYER   |
|-----------------------|
| - Remove duplicates   |
| - Trim / sanitize     |
| - Limit review count  |
+-----------+-----------+
            |
            | Structured Reviews Array
            v
+-------------------------------+
|   AI CALL #1 – INSIGHTS       |
|-------------------------------|
| Extract:                       |
| - Repeated phrases             |
| - Benefits                     |
| - Trust signals                |
| - Emotions / Keywords          |
+-----------+-------------------+
            |
            | Insight JSON (Source of Truth)
            v
+-------------------------------+
|  AI CALL #2 – AD GENERATOR    |
|-------------------------------|
| Input:                         |
| - Insight JSON                 |
| - Business Context             |
| Output:                        |
| - Text Ads                     |
| - Marketing Copy               |
| - Proof Phrases                |
+-----------+-------------------+
            |
            | Core Structured Output
            v
      +-----+-----------------------------+
      |                                   |
      v                                   v
+-------------------+          +----------------------+
| JSON FORMATTER    |          | TEXT FORMATTER       |
|-------------------|          |----------------------|
| Structured Output |          | Ad Blocks            |
| API Friendly      |          | Marketing Paragraph  |
+---------+---------+          +----------+-----------+
          |                               |
          +---------------+---------------+
                          |
                          | Headline / Tone
                          v
              +-------------------------------+
              | AI CALL #3 – IMAGE GENERATOR  |
              |-------------------------------|
              | Output: Ad Creatives          |
              +---------------+---------------+
                              |
                              | Final Response Bundle
                              v
+----------------------------------------------------+
|                    FRONTEND UI                     |
|----------------------------------------------------|
| Tabs:                                              |
| 1. Text Ads                                        |
| 2. Marketing Copy                                  |
| 3. Structured JSON                                 |
| 4. Image Creatives                                 |
+----------------------------------------------------+
                              |
                              v
+-------------------------------+
|        MINI SDK LAYER         |
|-------------------------------|
| generateAds(context,reviews)  |
| → Calls Backend API           |
+-------------------------------+
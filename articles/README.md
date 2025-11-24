# Perigon News Articles dataset extracted from the [Perigon API](https://perigon.io/docs).

- **✅ Enriched news articles with AI**
- **✅ Includes categories & sentiments**
- **✅ Contextual intelligence**
- **✅ Articles collected from 200k sources worldwide**

---

# Perigon API Response Structure

The API returns a JSON object containing a status code, result counts, and an array of news articles.

## 1. Root Object
The top-level wrapper for the request.

| Field | Type | Description |
| :--- | :--- | :--- |
| **`status`** | Integer | HTTP response status (e.g., `200`). |
| **`numResults`** | Integer | Total number of articles matching the query. |
| **`articles`** | Array | List of article objects. |

---

## 2. The Article Object
Each item inside the `articles` array contains the following data:

### A. Core Metadata
Basic details about the article and its source.

* **`articleId`**: Unique identifier for the article.
* **`title`**: The headline.
* **`url`**: Direct link to the source.
* **`pubDate`**: ISO timestamp of publication.
* **`language`**: Language code (e.g., `en`).
* **`source`**: Object containing publisher details:
  * `domain`: The website (e.g., `forbes.com`).
  * `paywall`: Boolean indicating if content is locked.
  * `location`: Publisher location (City, State, Country).

### B. Content
The text data of the news story.

* **`description`**: A short teaser/intro.
* **`content`**: The full body text.
* **`summary`**: AI-generated concise summary.
* **`translation`**: (If applicable) Translated text fields.

### C. Intelligence & NLP
Enriched data extracted by Perigon's AI.

* **`sentiment`**: Sentiment analysis scores (0-1).
  * *Keys:* `positive`, `negative`, `neutral`.
* **`entities`**: Detected People, Organizations, and Locations.
* **`companies`**: Business data including stock symbols (e.g., `NKE`) and domains.
* **`keywords`**: Important keywords with relevance weights.
* **`categories`**: General classification (e.g., `Finance`).
* **`highlights`**: Snippets of text that matched the search query.

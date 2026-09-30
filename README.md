# Reddit Marketing Research and Opportunity Finder

A web application built with Python and Flask that helps automate Reddit research for marketing.

The application takes keywords from an Excel file, searches Reddit for related discussions, and uses Google Gemini AI to identify posts that could be useful for marketing. It also provides a confidence score, explains why a post may be relevant, and suggests how the discussion could potentially be approached.

## What the application does

The main purpose of this application is to reduce the amount of manual work involved in finding useful Reddit discussions.

Instead of searching Reddit manually for every keyword, the user can upload an Excel file containing keywords and let the application handle the search and initial analysis.

The application then:

1. Reads keywords from an Excel file
2. Searches Reddit using the Reddit API
3. Finds posts related to each keyword
4. Filters out posts with very low engagement
5. Uses Google Gemini AI to analyze the posts
6. Determines whether a post could be relevant for marketing
7. Provides a confidence score and explanation
8. Generates a marketing suggestion
9. Displays the results
10. Allows the results to be downloaded as an Excel file

## How it works

The workflow is fairly simple:

Excel file

↓

Keywords are extracted

↓

Reddit is searched using PRAW

↓

Relevant posts are collected

↓

Gemini AI analyzes each post

↓

Relevant opportunities are identified

↓

Results are displayed

↓

Results can be downloaded as an Excel file

## Main features

Excel keyword upload

The application accepts Excel files with a column named Keyword. The keywords from this column are automatically extracted and used for the Reddit search.

Reddit search

The application uses PRAW, the Python Reddit API Wrapper, to search Reddit for posts related to the provided keywords.

AI based analysis

Google Gemini is used to analyze the title and content of Reddit posts. The application checks whether the discussion could be relevant to the service being marketed.

For relevant posts, the application provides:

Relevance

Confidence score

Reason for relevance

Marketing suggestion

Reddit post details

The results include useful information such as the subreddit, post score, number of comments, post title, post content, creation date and Reddit URL.

Excel export

After the search is completed, the results can be downloaded as an Excel file for further analysis or reporting.

Background processing

The Reddit search runs in a background thread so that the application can continue showing the search progress while the analysis is running.

## Example input

The Excel file should contain a column named Keyword.

Example:

| Keyword               |
| --------------------- |
| Data Analytics        |
| Python Automation     |
| Business Intelligence |
| Data Visualization    |
| Reporting Automation  |

The application reads these keywords and searches Reddit for related discussions.

## Example analysis

For a Reddit post, the application may return something similar to:

Relevant: Yes

Confidence: 0.82

Reason: The user is looking for a solution related to automated data processing.

Marketing Suggestion: Provide helpful information about how automation could solve the problem discussed in the post.

The confidence score and AI generated suggestions are intended to assist with research and should be reviewed before taking any marketing action.

## Technologies used

Python

Flask

PRAW

Pandas

Google Gemini API

HTML

CSS

OpenPyXL

## Project structure

```text
reddit-marketing-tool/

app.py

templates/
    index.html
    results.html

static/
    ...

requirements.txt
README.md
.gitignore
```

## Running the application

First clone the repository.

```bash
git clone https://github.com/your-username/reddit-marketing-tool.git
cd reddit-marketing-tool
```

Create a virtual environment.

```bash
python -m venv venv
```

For Windows:

```bash
venv\Scripts\activate
```

Install the required packages.

```bash
pip install -r requirements.txt
```

Set up the required environment variables for Reddit and Google Gemini.

The application uses:

```text
REDDIT_CLIENT_ID
REDDIT_SECRET
REDDIT_USER_AGENT
GEMINI_API_KEY
FLASK_SECRET_KEY
```

Then start the application.

```bash
python app.py
```

Open the application in your browser at:

```text
http://localhost:5000
```

## Security

API credentials are stored using environment variables and should not be added directly to the source code.

Make sure your `.env` file and other sensitive files are included in `.gitignore`.

```text
.env
venv/
__pycache__/
*.pyc
```

Do not upload API keys, company data, private credentials or other sensitive information to the repository.

## Possible future improvements

Some improvements I would like to add in the future include:

Subreddit specific searches

Better duplicate post detection

Sentiment analysis

More detailed marketing opportunity analysis

Search history

Database integration

Analytics dashboard

Scheduled searches

User authentication

More advanced filtering and ranking

## About the project

I built this project to automate a repetitive Reddit research process and make it easier to find potentially useful discussions from a large number of search results.

The project combines API integration, data processing, web development and AI based analysis into one application.

Built with Python, Flask, PRAW, Pandas, Google Gemini, HTML and CSS.


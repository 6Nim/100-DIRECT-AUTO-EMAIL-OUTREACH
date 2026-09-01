# Automated Website Hosting Auditor & Outreach Engine

An automated lead generation and outreach solution built with **Google Apps Script**, **Google Sheets**, and **Gemini 1.5 Flash AI**. 

This tool scans a list of websites in bulk, detects server performance issues (high TTFB/latency, HTTP errors, SSL issues), automatically extracts the clean brand name, generates personalized micro-outreach emails via Gemini AI, and sends them directly through Gmail.

---

## ✨ Features

* **⚡ Automated Hosting Audit Engine:** Checks target websites for server response latency (TTFB > 0.8s), HTTP server errors (5xx), and SSL/Redirect issues.
* **🏷️ Smart Brand Name Extraction:** Automatically parses URLs to extract clean brand names (e.g., converts `https://www.examplebrand.com/page` to `Examplebrand`).
* **🤖 AI-Personalized Cold Outreach:** Integrates with **Gemini 1.5 Flash API** to generate friendly, non-spammy, high-converting outreach emails customized to each target's specific technical issue.
* **🛡️ Built-in API Rate Limit Protection:** Includes strategic 2-second and 1.5-second execution delays (`Utilities.sleep`) to prevent API quota blocks and Gmail rate limits.
* **⚡ Fail-Safe Fallback Mechanism:** Features a default cold email template if the AI API call drops, ensuring 100% email delivery.
* **📊 Live Sheet Tracking:** Updates audit logs and outreach status (`Sent`, `No Issue Detected`, or error logs) directly in Google Sheets in real-time.

---

## 🛠️ Google Sheet Setup

Organize your Google Sheet columns as follows:

| Column A | Column B | Column C | Column D |
| :--- | :--- | :--- | :--- |
| **Website URL** | **Client Email** | **Audit Results** | **Status** |
| `https://example.com` | `contact@example.com` | *(Auto-filled)* | *(Auto-filled)* |

---

## 🚀 Getting Started

1. Open your Google Sheet and go to **Extensions > Apps Script**.
2. Paste the script into the editor (`Code.gs`).
3. Replace `YOUR_GEMINI_API_KEY_HERE` with your valid **Gemini API Key**.
4. Run `runGenuineIssueWorkflow()`.
5. Authorize the script when prompted by Google to grant Gmail & UrlFetch permissions.

---

## 🧰 Tech Stack

* **Language:** JavaScript / Google Apps Script
* **AI Engine:** Google Gemini 1.5 Flash API
* **Integrations:** Google Sheets API, Gmail API (`MailApp`), Google `UrlFetchApp`Gmail.

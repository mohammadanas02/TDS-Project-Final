# AI-Powered Automation Agent

## Overview
This project is an AI-powered automation agent that exposes an API with endpoints to execute plain-English tasks and read file contents. The agent leverages a Large Language Model (LLM) to interpret task descriptions and execute multi-step processes.

## API Endpoints

### `POST /run?task=<task description>`
Executes a plain-English task.

#### Responses:
- **200 OK**: Task executed successfully.
- **400 Bad Request**: Task contains an error.
- **500 Internal Server Error**: Agent encountered an error.

### `GET /read?path=<file path>`
Returns the content of the specified file.

#### Responses:
- **200 OK**: File content returned as plain text.
- **404 Not Found**: File does not exist.

---

## Phase A: Handle Operations Tasks
The agent automates the following operations tasks:

1. **Install `uv` (if required) and run `datagen.py`** with `${user.email}` as the argument.
2. **Format `/data/format.md`** using `prettier@3.4.2`.
3. **Count Wednesdays in `/data/dates.txt`** and save to `/data/dates-wednesdays.txt`.
4. **Sort contacts in `/data/contacts.json`** by `last_name` and `first_name`, save to `/data/contacts-sorted.json`.
5. **Extract first line of 10 most recent `.log` files** from `/data/logs/` into `/data/logs-recent.txt`.
6. **Index Markdown files** in `/data/docs/` by extracting first `H1` title and saving to `/data/docs/index.json`.
7. **Extract sender’s email** from `/data/email.txt` using an LLM, save to `/data/email-sender.txt`.
8. **Extract credit card number** from `/data/credit-card.png` using an LLM, save to `/data/credit-card.txt`.
9. **Find most similar comments** in `/data/comments.txt` using embeddings, save to `/data/comments-similar.txt`.
10. **Calculate total sales for 'Gold' tickets** from `/data/ticket-sales.db` and save to `/data/ticket-sales-gold.txt`.

---

## Phase B: Handle Business Tasks

### Security Constraints
- **B1:** Data outside `/data` is never accessed.
- **B2:** Data is never deleted.

### Additional Tasks
- **Fetch data from an API and save it**
- **Clone a git repo and make a commit**
- **Run a SQL query on SQLite/DuckDB**
- **Scrape a website for data**
- **Compress or resize an image**
- **Transcribe audio from an MP3 file**
- **Convert Markdown to HTML**
- **Write an API endpoint to filter CSV and return JSON**

The business team may add more tasks, and handling them will result in a bonus.

---

## Installation & Usage

### Prerequisites
- Python 3.9+
- Docker

### Setup
1. Clone the repository:
   ```sh
   git clone <repository-url>
   cd <repository>

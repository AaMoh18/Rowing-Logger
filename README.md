# Rowing Performance Logger

A simple, user-friendly web application for logging and viewing rowing session data. This tool is designed for teams or individuals to track their performance over time, with all data being stored and retrieved from a shared Google Sheet in real-time.

[Link to Live Demo](https://rowing-log.netlify.app/)

## Features

* Centralized Data: All entries are stored in a single, shared Google Sheet, making it easy to manage and access the data.

* Dynamic Data Table: View all logged activities in a real-time table that updates automatically.

* Advanced Sorting & Filtering: Instantly sort the data by latest date, oldest date, or alphabetically by name. You can also filter the table to show entries for a specific person.

* Smart Name Grouping: The application intelligently groups similar names (e.g., "Jane" and "Jane Doe") to consolidate their stats.

* Performance Insights:

* Frequency Color-Coding: Names in the table are automatically color-coded based on how frequently each person logs their sessions.

* Day Span Counter: A counter displays the total number of days from the very first logged activity to the most recent one, showing the total duration of the training period.

* Dual Theming:

* Light Mode: A clean, stylish theme with a Japanese wave pattern background.

* Dark Mode: A sleek, modern theme with a starry background and semi-transparent, blurred cards.

* User-Friendly Interface:

* Supports logging multiple timings in a single session.

* Remembers previously entered names to suggest them automatically.

## Tech Stack

* Frontend: HTML5, Tailwind CSS, Vanilla JavaScript

* Backend: Google Apps Script

* Database: Google Sheets

## Setup Guide

To get this project running, you need to link the HTML file to your own Google Sheet.

### Step 1: Set Up the Google Sheet

Create a new Google Sheet.

Name the first five columns in the first row exactly as follows:
Timestamp, Name, Date, Distance, Time

### Step 2: Create the Google Apps Script

In your Google Sheet, go to Extensions > Apps Script.

A new script project will open. Delete any existing code in the Code.gs file.

Copy the entire contents of the Code.gs file from this project and paste it into the script editor.

Click the Deploy button, select New deployment.

In the deployment settings:

* Type: Select Web app.

* Execute as: Select Me.

* Who has access: Select Anyone.

Click Deploy.

Authorize the script's permissions when prompted.

Copy the generated Web app URL. You will need this for the next step.

### Step 3: Configure the HTML File

Open the index.html file.

Find the following line in the <script> section at the bottom:

```
const SCRIPT_URL = 'PASTE_YOUR_WEB_APP_URL_HERE';

```

Replace the placeholder text with the Web app URL you copied from the Apps Script deployment.

### Step 4: Deploy to GitHub Pages

Create a new public repository on GitHub.

Upload the configured index.html file to the repository.

Go to your repository's Settings tab.

In the left sidebar, click on Pages.

Under "Build and deployment," select the main branch as your source and click Save.

Your website will be live in a few minutes at the URL provided by GitHub Pages (e.g., https://<your-username>.github.io/<your-repo-name>/).

## How to Use

Open the live website URL.

Enter your name and the date of the session.

Specify the number of timings you want to log.

For each timing, select a preset distance or enter a custom one, and input the time taken.

Click Log Activity. The data will be sent to the Google Sheet and the table will update automatically.

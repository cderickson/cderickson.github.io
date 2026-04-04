---
layout: splash
title: "MTGO-Tracker"
sitemap: false
permalink: /mtgo-tracker/
author_profile: false
---

{% include toc %}
<span class="image main"><img src="_images/pic22.jpg" alt="" style="border: 3px solid black;" /></span>

# Overview

<p>MTGO-Tracker is an <strong>analytics tool</strong> used to process raw data for Magic: the Gathering Online. Players can import and parse log files created during online play and store resulting information into a local database for self-analysis.</p>
<p>See <strong><a href="https://github.com/cderickson/MTGO-Tracker">GitHub Repository</a></strong>.</p>

<p>
    <strong>Processed data</strong> is stored in five (5) tables:<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Matches<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Games<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Plays<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Drafts<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Draft Picks
</p>
<p>This data will help you track your results, evaluate your performance, and analyze your play patterns.</p>
<p>Built-in dashboards are included to view and track <strong>Match History (Overall or by Format)</strong>, <strong>Match History vs. Opponent</strong>, <strong>Match/Game Performance Data</strong>, <strong>Play Pattern Data</strong>, and <strong>Card Data</strong>.</p>
<p>Generated tables can be <b>exported</b> to .csv or .xlsx to allow you to manipulate the data yourself, run your own queries and build your own visualizations.</p>
<div style="text-align: center;">
    <span class="image object"><img src="../images/vintage1.png1" alt="MTGO-Tracker" 
        style="height: 100%; width: 100%; object-fit: cover; border: 3px solid black;" /></span>
</div>

## Limitations

<p><b>Importing</b>: Some data (e.g. Deck Names, Match Format) cannot be read from GameLog files explicitly. These columns import as NA by default and are input manually by the user.</p>
<p><b>Deck Names</b>: Included is a tool to set best guess deck names by comparing card data with MTG Goldfish decklists, but this is not always accurate. Card data is saved for every match to assist with data entry for old matches.</p>
<p><b>Outdated</b> GameLogs: My test data includes my own personal data from January 2021 to current. Older files may have been formatted differently and may not import correctly. (For example, I know formatting changed when the London Mulligan was implemented in July 2019)</p>

<h2>Release History</h2>
<p>
    <strong>MTGO-Tracker-v.16 (Oct 2023)</strong> - <strong><a href="https://github.com/cderickson/MTGO-Tracker/releases/tag/v.16">Change Log</a></strong>, <b><a href="https://github.com/cderickson/MTGO-Tracker/releases/download/v.16/MTGO-Tracker-v.16.rar">Download</a></b><br>
    <strong>MTGO-Tracker-v.15</strong> - <strong><a href="https://github.com/cderickson/MTGO-Tracker/releases/tag/v.15">Change Log</a></strong><br>
    <strong>MTGO-Tracker-v.14</strong> - <strong><a href="https://github.com/cderickson/MTGO-Tracker/releases/tag/v.14">Change Log</a></strong><br>
    <strong>MTGO-Tracker-v.13</strong> - <strong><a href="https://github.com/cderickson/MTGO-Tracker/releases/tag/v.13">Change Log</a></strong><br>
    <strong>MTGO-Tracker-v.12</strong> - <strong><a href="https://github.com/cderickson/MTGO-Tracker/releases/tag/v.12">Change Log</a></strong><br>
    <strong>MTGO-Tracker-v.4.0</strong> - <strong><a href="https://github.com/cderickson/MTGO-Tracker/releases/tag/v.4.0">Change Log</a></strong><br>
    <strong>MTGO-Tracker 2022-v.3.2</strong> - <strong><a href="https://github.com/cderickson/MTGO-Tracker/releases/tag/2022-v.3.2">Change Log</a></strong><br>
    <strong>MTGO-Tracker 2022-v.3.1</strong> - <strong><a href="https://github.com/cderickson/MTGO-Tracker/releases/tag/2022-v.3.1">Change Log</a></strong><br>
    <strong>MTGO-Tracker 2022-v.3.0</strong> - <strong><a href="https://github.com/cderickson/MTGO-Tracker/releases/tag/2022-v.3.0">Change Log</a></strong><br>
    <strong>MTGO-Tracker 2022-v.2.0</strong> - <strong><a href="https://github.com/cderickson/MTGO-Tracker/releases/tag/2022-v.2.0">Change Log</a></strong><br>
    <strong>MTGO-Tracker 2022-v.1.2</strong> - <strong><a href="https://github.com/cderickson/MTGO-Tracker/releases/tag/2022-v.1.2">Change Log</a></strong><br>
    <strong>MTGO-Tracker 2022-v.1.1</strong> - <strong><a href="https://github.com/cderickson/MTGO-Tracker/releases/tag/2022-v.1.1">Change Log</a></strong><br>
    <strong>MTGO-Tracker 2022-v.1.0</strong> - <strong><a href="https://github.com/cderickson/MTGO-Tracker/releases/tag/2022-v.1.0">Change Log</a></strong><br>
    <strong>MTGO-Tracker v.1.0.2</strong> - <strong><a href="https://github.com/cderickson/MTGO-Tracker/releases/tag/v1.0.2">Change Log</a></strong><br>
    <strong>MTGO-Tracker v.1.0.1</strong> - <strong><a href="https://github.com/cderickson/MTGO-Tracker/releases/tag/v1.0.1">Change Log</a></strong><br>
    <strong>MTGO-Tracker v.1.0.0</strong> - <strong><a href="https://github.com/cderickson/MTGO-Tracker/releases/tag/v1.0.0">Change Log</a></strong>
</p>
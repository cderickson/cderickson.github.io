---
layout: splash
title: "Mox Data"
sitemap: false
permalink: /mox-data/
author_profile: false
---

<span class="image main"><img src="../images/mox-data-header.png" alt="" style="border: 3px solid black;" /></span>
{% unless page.header.overlay_color or page.header.overlay_image %}
<h1 class="page__title">{{ page.title }}</h1>
{% endunless %}
{% include toc %}

<p><strong>Mox Data</strong> is a cloud-based ingestion and analytics platform for Magic: The Gathering Online (MTGO). Players upload raw MTGO GameLog and DraftLog files which are then parsed into structured records, stored in PostgreSQL, and presented to users through interactive tables and dashboards. This application allows players to analyze their play-by-play data, a level of granularity which has not always been available.</p>

<p>This project builds on the original <strong><a href="https://github.com/cderickson/MTGO-Tracker">MTGO-Tracker</a></strong> application, incorporating many of the same workflows.</p>

<p>See <strong><a href="https://github.com/cderickson/Mox-Data.com">GitHub repository</a></strong>.</p>
<br>

## Process

- <strong>Ingest</strong> user-uploaded MTGO log files, archiving them in <strong>S3</strong>.
- <strong>Parse &amp; transform</strong> logs into matches, games, plays, drafts, and picks.
- <strong>Load</strong> structured rows into an <strong>RDS PostgreSQL</strong> database.
- <strong>Enrich</strong> data through built-in data-cleaning functionality.
- <strong>Present</strong> data back to users through web UI: tables, exports, and analytics dashboards views.

<p>The application is implemented in <strong>Python</strong> with <strong>Flask</strong>, <strong>SQLAlchemy</strong>, and <strong>Flask-Migrate</strong> (Alembic). Production HTTP is served by <strong>Gunicorn</strong> inside a <strong>Docker</strong> container image.</p>

## Data sources

<p>Primary inputs are <strong>MTGO client log files</strong> produced during online play. Finalized dataset will also include user enhancements.</p>

## Architecture

<p>Mox Data is deployed on <strong>AWS</strong> using <strong>ECS</strong> for web and worker services, <strong>ECR</strong> for Docker container image deployment, <strong>Amazon RDS</strong> (<strong>PostgreSQL</strong>) database, <strong>S3</strong> for storage, and <strong>ElastiCache</strong> for Celery broker and result backend.</p>

## Database Schema

<div class="table-wrapper" style="display: flex; justify-content: center;">
    <table style="margin: 0 auto;">
        <thead>
            <tr>
                <th>Table</th>
                <th>Description</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td><b>Player</b></td>
                <td>User account information.</td>
            </tr>
            <tr>
                <td><b>Match</b></td>
                <td>Match header: players, format, wins, deck information.</td>
            </tr>
            <tr>
                <td><b>Game</b></td>
                <td>Per-game row data (mulligans, on-play/draw, winner, etc.).</td>
            </tr>
            <tr>
                <td><b>Play</b></td>
                <td>Play-by-play actions (casts, lands, triggers, etc.).</td>
            </tr>
            <tr>
                <td><b>Draft</b></td>
                <td>Draft metadata.</td>
            </tr>
            <tr>
                <td><b>Pick</b></td>
                <td>Draft picks.</td>
            </tr>
            <tr>
                <td><b>Game Actions</b></td>
                <td>Raw end-of-game action text used for workflows such as missing winner resolution.</td>
            </tr>
            <tr>
                <td><b>Removed</b></td>
                <td>Tracks removed or rejected match records.</td>
            </tr>
            <tr>
                <td><b>Cards Played</b></td>
                <td>Aggregated card activity summaries per match.</td>
            </tr>
            <tr>
                <td><b>Task History</b></td>
                <td>Celery/async job history for uploads and processing.</td>
            </tr>
            <tr>
                <td><b>Export Job</b></td>
                <td>Async export jobs (status, S3 keys, expiry).</td>
            </tr>
            <tr>
                <td><b>MULTIFACED_CARDS</b></td>
                <td>Reference mapping for split/transform/DFC/MDFC/adventure card names.</td>
            </tr>
            <tr>
                <td><b>INPUT_OPTIONS</b></td>
                <td>Configurable option lists for UI-driven fields.</td>
            </tr>
            <tr>
                <td><b>ALL_DECKS</b></td>
                <td>Curated deck list snapshots by month/format. Used to apply best guess deck names.</td>
            </tr>
        </tbody>
    </table>
</div>
<br>

<br>
<p>See <strong><a href="data-dictionary/">Data Dictionary</a></strong> for feature definitions.</p>

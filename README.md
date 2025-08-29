🎵 Spotify Advanced SQL & Query Optimization – P6
📌 Project Overview

This project focuses on SQL-based analysis of a Spotify dataset, containing information about tracks, albums, artists, and multiple engagement metrics. The goal is to practice advanced SQL techniques ranging from simple retrieval queries to complex analytical queries with window functions and optimizations.

The work is divided into 3 main stages:

Data Structuring – Creating and organizing the dataset in PostgreSQL.

SQL Querying – Writing queries of increasing complexity (Easy → Medium → Advanced).

Performance Optimization – Applying indexing and execution plan analysis to improve query efficiency.

📂 Dataset Information

The dataset includes attributes related to music tracks and user interaction:

Artist / Track / Album / Album Type

Musical properties: danceability, energy, loudness, tempo, valence, acousticness, etc.

Engagement metrics: views, likes, comments, streams.

Other features: licensed/official flags, platform usage (Spotify, YouTube, etc.).

The schema used in PostgreSQL:

DROP TABLE IF EXISTS spotify;

CREATE TABLE spotify (
    artist VARCHAR(255),
    track VARCHAR(255),
    album VARCHAR(255),
    album_type VARCHAR(50),
    danceability FLOAT,
    energy FLOAT,
    loudness FLOAT,
    speechiness FLOAT,
    acousticness FLOAT,
    instrumentalness FLOAT,
    liveness FLOAT,
    valence FLOAT,
    tempo FLOAT,
    duration_min FLOAT,
    title VARCHAR(255),
    channel VARCHAR(255),
    views FLOAT,
    likes BIGINT,
    comments BIGINT,
    licensed BOOLEAN,
    official_video BOOLEAN,
    stream BIGINT,
    energy_liveness FLOAT,
    most_played_on VARCHAR(50)
);

📝 SQL Query Challenges

Queries were categorized into Easy, Medium, and Advanced levels:

🔹 Easy Level

Tracks with more than 1B streams

Album–artist listing

Total comments for licensed = TRUE tracks

Tracks belonging to single-type albums

Track count per artist

🔹 Medium Level

Average danceability per album

Top 5 tracks by energy score

Tracks with views & likes where official_video = TRUE

Total views aggregated by album

Tracks streamed more on Spotify vs YouTube

🔹 Advanced Level

Top 3 most-viewed tracks per artist (using window functions)

Tracks with above-average liveness

Energy range (max–min) per album using a CTE

Tracks with energy-to-liveness ratio > 1.2

Cumulative likes ordered by views (window function)

⚡ Query Optimization

As part of performance tuning, queries were tested with EXPLAIN ANALYZE before and after optimization.

Step 1: Baseline Analysis

Example: Query filtered rows using the artist column.

Execution time: ~7 ms

Planning time: 0.17 ms

Step 2: Indexing

To optimize retrieval, an index was added:

CREATE INDEX idx_artist ON spotify(artist);

Step 3: Post-Optimization Results

Execution time reduced to ~0.15 ms

Planning time reduced to ~0.15 ms

Step 4: Performance Visualization

A comparison graph (Before vs After Index) clearly shows reduced query times, highlighting the impact of indexing in large datasets.

🛠️ Tech Stack

Database: PostgreSQL

Tools: pgAdmin 4 / SQL editor

Core SQL Features: Joins, Aggregations, Subqueries, Window Functions, CTEs

Optimization: Indexing, Execution Plans

🚀 How to Run This Project

Install PostgreSQL & pgAdmin.

Create schema & load dataset.

Run queries (Easy → Medium → Advanced).

Test query performance using EXPLAIN ANALYZE.

Apply optimizations (indexing, restructuring).

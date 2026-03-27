# bluesky-stats

Tracks daily Bluesky follower counts for the CGD account (`cgdev.org`).

## Why

Sprout Social, CGD's social media management platform, does not track Bluesky follower counts. This repo fills that gap by collecting the data automatically so we have a historic record.

## How it works

A GitHub Actions workflow runs daily at 8:00 AM UTC. It calls the public Bluesky API, extracts the follower count, following count, and post count for `cgdev.org`, and appends a timestamped row to a CSV file, which is then committed back to this repository automatically.

## Data

Follower counts are stored in `data/followers.csv` with the following columns:

| Column | Description |
|---|---|
| `timestamp` | UTC datetime of the snapshot |
| `followers` | Number of followers |
| `following` | Number of accounts followed |
| `posts` | Total number of posts |

## Maintainer

Jeremy Gaines — jgaines@cgdev.org

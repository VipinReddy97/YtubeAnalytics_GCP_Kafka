# YouTube Analytics with Kafka and Telegram Notifications

This Python-based project aims to fetch real-time YouTube metrics like likes, views, comments, and favorites, and then streams this data via Kafka. The data is then processed using ksqlDB, and the results are sent to a Telegram bot for real-time notifications.

## Table of Contents
- [System Architecture](#system-architecture)
- [Requirements](#requirements)
- [Getting Started](#getting-started)
- [Configuration](#configuration)
- [Running the Code](#running-the-code)
- [How It Works](#how-it-works)


## System Architecture
![YouTube Analytics Architecture](ytanalytics.png)

## Requirements
- **Python 3.10** (minimum)
- **Kafka**
- **Telegram API**
- **Docker**
- **Confluent Containers** (Zookeeper, Kafka, Schema Registry, Connect, ksqlDB, Control Center)

## Getting Started

To get started, follow these steps:

```sh
# 1. Clone the Repository
git clone https://github.com/VipinReddy97/YtubeAnalytics_GCP_Kafka.git

# 2. Install Python Dependencies
pip install -r requirements.txt

# 3. Set Up Docker and Confluent Containers
# Ensure Docker is installed and set up on your machine. You'll also need to set up Confluent containers (Zookeeper, Kafka, Schema Registry, Connect, ksqlDB, Control Center).

# 4. Configure the Environment
# Open the configuration file `config/config.local` and set the following parameters:
# YOUTUBE_API_KEY: Your YouTube API Key
# PLAYLIST_ID: The YouTube playlist ID you want to track
# Additionally, set up your Kafka server address in the main script. By default, it's set to `localhost:9092`.

## How it Works
Fetches video data from the YouTube API using the provided playlist ID. Streams the data to a Kafka topic for further processing. Another component (discussed in the video but not covered here) will consume data from this Kafka topic and run real-time analytics using ksqlDB. Finally, the results of the analytics are forwarded to Telegram to provide real-time alerts.


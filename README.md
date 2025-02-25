# FxFurTrack

This project provides a scraping service that extracts OpenGraph (OG) metadata from FurTrack pages. It uses a **Master-Worker** architecture where the master handles requests and workers run Puppeteer to fetch and extract metadata dynamically.
---

## Installation & Setup

### **1. Prerequisites**
Ensure you have the following installed:
- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/install/)

### **2. Clone the Repository**
```bash
git clone https://github.com/blumlaut/fxfurtrack.git
cd fxfurtrack
```

### **3. Start the Services**
Run the following command to build and start all services:
```bash
docker-compose up --build
```
This will start:
- **Redis** (for job queuing and caching)
- **Master API** (handles requests)
- **Worker(s)** (scrape OpenGraph metadata using Puppeteer)

To run with multiple workers:
```bash
docker-compose up --scale worker=5
```

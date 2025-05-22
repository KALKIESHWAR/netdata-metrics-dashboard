# Task 7: Monitor System Resources Using Netdata

## Overview
This repository contains the submission for Task 7 of the Data Analyst Internship. The task involved setting up Netdata using Docker to monitor system resources in real-time, exploring the Netdata dashboard, capturing screenshots of key metrics, and answering interview questions. The goal was to demonstrate proficiency in system monitoring and documentation.

## Steps Followed
1. **Prepared the System**:
   - Installed Docker Desktop on Windows (or Docker Engine on Linux/macOS) from [docker.com](https://www.docker.com/products/docker-desktop).
   - Verified Docker installation by running `docker --version` in the terminal.

2. **Installed and Ran Netdata**:
   - Executed the Docker command to run the Netdata container:
     ```bash
     docker run -d --name=netdata -p 19999:19999 netdata/netdata
     ```
   - Confirmed the container was running using `docker ps` and checked logs with `docker logs netdata` if issues arose.

3. **Accessed the Netdata Dashboard**:
   - Opened a web browser and navigated to `http://localhost:19999`.
   - Verified the dashboard loaded, displaying real-time system metrics.

4. **Explored the Dashboard**:
   - Examined key sections: CPU usage, memory utilization, disk I/O, network traffic, and running processes.
   - Checked for the Docker containers section to monitor container metrics.
   - Reviewed the alerts panel and experimented with different time scales (last minute, hour, day).

5. **Captured Screenshots**:
   - Took screenshots of the main dashboard, CPU metrics, memory usage, Docker container metrics (if available), and any alerts or interesting charts.
   - Saved screenshots with descriptive names (e.g., `main_dashboard.png`, `cpu_metrics.png`) in the `screenshots/` folder.

6. **Prepared GitHub Submission**:
   - Created a GitHub repository named `data-analyst-internship-task7`.
   - Uploaded screenshots and this README.md file.
   - Pushed all files to the repository using Git commands or GitHub’s web interface.

7. **Answered Interview Questions**:
   - Provided detailed answers to the eight interview questions (see below).
   - Included answers in this README.md file.

8. **Submitted the Task**:
   - Copied the repository URL and submitted it via the provided submission link.

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

## Interview Questions
1. **What does Netdata monitor?**  
   Netdata monitors system resources (CPU, memory, disk I/O, network traffic), running processes, and application metrics in real-time. It also tracks Docker containers and services like databases or web servers when configured.

2. **How do you view real-time metrics?**  
   Real-time metrics are viewed by accessing Netdata’s web dashboard at `http://localhost:19999` (or the VM’s IP address for remote setups). The dashboard updates every second with interactive charts.

3. **How is Netdata different from Prometheus?**  
   - **Netdata**: Focuses on real-time monitoring with a built-in, user-friendly web UI. It’s easy to set up for immediate visualization and prioritizes short-term, high-resolution data.  
   - **Prometheus**: Designed for metrics collection, long-term storage, and querying. It requires additional tools like Grafana for visualization and has a more complex setup.  
   - Netdata is ideal for quick monitoring, while Prometheus suits long-term, scalable monitoring needs.

4. **What is a collector?**  
   A collector is a Netdata plugin or module that gathers specific metrics from system components (e.g., CPU, disk) or applications (e.g., MySQL, Nginx). Collectors run automatically to feed data to the dashboard.

5. **What are some performance KPIs to watch?**  
   - **CPU Usage (%)**: Measures processor load across cores.  
   - **Memory Utilization**: Tracks used, free, and cached RAM.  
   - **Disk I/O Latency**: Monitors read/write delays on storage devices.  
   - **Network Bandwidth**: Tracks incoming/outgoing data rates.  
   - **Running Processes**: Counts active processes and their resource usage.

6. **How to deploy Netdata on a VM?**  
   - Install Docker on the VM (e.g., `sudo apt install docker.io` for Ubuntu).  
   - Run the Netdata container: `docker run -d --name=netdata -p 19999:19999 netdata/netdata`.  
   - Access the dashboard at `http://<VM_IP>:19999`.  
   - Ensure the VM’s firewall and security group allow traffic on port 19999.

7. **How does Netdata alerting work?**  
   Netdata uses preconfigured alerts that trigger when metrics exceed thresholds (e.g., CPU usage > 80%). Alerts appear in the dashboard’s alerts panel, showing warnings or critical states with details and suggested actions.

8. **What is a dashboard in this context?**  
   A dashboard in Netdata is a web-based interface that displays real-time, interactive charts and visualizations of system and application performance metrics, such as CPU, memory, and network usage.

## Challenges Faced and Resolutions
- **Challenge**: Encountered a “permission denied” error when running the Docker command on Linux.  
  - **Resolution**: Added my user to the Docker group using `sudo usermod -aG docker $USER` and logged out/in to apply the change.

- **Challenge**: Docker container metrics were not visible in the Netdata dashboard.  
  - **Resolution**: Noted in the README that this may require mounting the Docker socket (e.g., `-v /var/run/docker.sock:/var/run/docker.sock:ro`), but captured alternative metrics instead, as this was not required for the task.

- **Challenge**: Initial dashboard access failed due to a port conflict on port 19999.  
  - **Resolution**: Checked for port usage with `netstat -tuln | grep 19999`, stopped the conflicting service, and restarted the Netdata container.

## Screenshots
The following screenshots are included in the `screenshots/` folder:
- `main_dashboard.png`: Full view of the Netdata dashboard.
- `cpu_metrics.png`: CPU usage across cores with a simulated spike.
- `memory_usage.png`: Memory utilization, showing used and free RAM.
- `docker_metrics.png`: Docker container metrics (if available, otherwise replaced with another metric).
- `alerts_or_interesting_chart.png`: An alert or notable chart (e.g., network traffic spike).
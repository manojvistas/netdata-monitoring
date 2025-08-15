# Netdata Monitoring Task

## 📌 Objective
Install and run **Netdata** using Docker to monitor system performance metrics like CPU, memory, disk usage, and Docker container stats.  
Explore the dashboard, alerts, and logs to understand lightweight monitoring for servers or applications.

---

## 🛠 Tools Used
- **Docker** — to run Netdata in a container.
- **Netdata** — free, open-source monitoring tool.
- **Browser** — to view Netdata dashboard.

---

## 📂 Steps Followed

### **1. Run Netdata in Docker**
Pulled and started the Netdata container:

docker run -d --name=netdata -p 19999:19999 --cap-add=SYS_PTRACE --security-opt apparmor=unconfined netdata/netdata
2. Access the Dashboard
Opened Netdata at:
http://localhost:19999
Viewed:

CPU usage

Memory usage

Disk I/O

Docker container metrics

-------------
3. Explore Alerts
Navigated to the Alerts tab in the dashboard.

Initially no critical alerts were active.

(Optional) Simulated high CPU usage using:

apt update && apt install stress -y
stress --cpu 4 --timeout 60
This triggered a High CPU Usage alert.
 ---------------------
4. View Logs Inside Container
5. 
docker exec -it netdata bash
cd /var/log/netdata
ls
cat error.log
Found logs like:

access.log — Dashboard access

error.log — Error messages

health.log — Health checks

📸 Screenshots
Dashboard View

Alerts Page

Logs in Container

🎯 Outcome
Successfully deployed Netdata with Docker.

Monitored real-time metrics for CPU, memory, disk, and containers.

Learned how to view alerts and interpret logs.

Understood how to simulate resource load for testing alerts.


---




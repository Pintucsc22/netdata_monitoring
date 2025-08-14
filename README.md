# Netdata Monitoring

## Objective

Install and use Netdata to monitor system and application performance metrics in real-time, including Docker container metrics.

## Tools Used

* Netdata (Docker container)
* Browser for dashboard access

## Steps Taken

1. **Installed and ran Netdata using Docker:**

```bash
docker run -d --name=netdata \
  -p 19999:19999 \
  --cap-add SYS_PTRACE \
  --security-opt apparmor=unconfined \
  -v /var/run/docker.sock:/var/run/docker.sock:ro \
  netdata/netdata
```

2. **Accessed the Netdata dashboard**
   Open a browser and go to:

```
http://<your-server-ip>:19999
```

3. **Verified Docker monitoring**

* Ensured Docker plugin is enabled in `netdata.conf`
* Mounted Docker socket (`/var/run/docker.sock`) for metrics

4. **Monitored system metrics**

* CPU usage
* Memory usage
* Network traffic
* Disk I/O

5. **Monitored Docker container metrics**

* CPU and memory per container
* Network I/O per container
* Disk I/O per container

---

## Screenshots

### Netdata Home Dashboard

![Netdata Home](/Screenshots/Dashboard.png)

### Docker Containers Metrics

![Docker Containers](/Screenshots/docker.png)

### Memory Usage

![Memory](/Screenshots/memory.png)

### CPU Usage

![CPU](/Screenshots/cpu.png)

### Network

![Network Disk](/Screenshots/Network.png)

---

## Observations

* Netdata provides **real-time monitoring** with minimal setup.
* Docker container metrics allow tracking resource usage per container.
* Dashboard is interactive and helps quickly identify performance bottlenecks.

---

## Conclusion

Netdata is an effective tool for monitoring both system and application performance. Running it in Docker makes setup easy, and integrating Docker metrics allows complete visibility into containerized workloads.


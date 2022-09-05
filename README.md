# Cray Boot Monitoring
## Installing Prometheus:

### Steps:

On the monitoring server, install the golang-github-prometheus-prometheus package
	
```bash
zypper in golang-github-prometheus-prometheus
```

Enable the Prometheus service:

```bash
systemctl enable --now prometheus
```

Check that the Prometheus interface is loading correctly. In your browser, navigate to the URL of the server where Prometheus is installed, and listen on port 9090

configure Prometheus in the static configuration file at `/etc/prometheus/prometheus.yml` and add the job name and targets for prometheus. Reference file location in repository - `/cray-boot-monitoring/configuration/Prometheus/prometheus.yml`.


## Installing Grok-exporter:

### Steps:

On the monitoring server, install the grok-exporter package in directory `/usr/local/bin`:

```bash
wget https://github.com/fstab/grok_exporter/releases/download/v1.0.0.RC2/grok_exporter-1.0.0.RC2.linux-amd64.zip
```

Extract the grok-exporter .tar file and move to grok exporter directory.

```bash
unzip grok_exporter-*.zip
```

Now, create a systemd service file for Grok Exporter so that (start, stop, restart, and add to startup) the node-exporter service with systemd is easily manageable.

To create a systemd service file grok-exporter.service, run the following command:

```bash
vi /etc/systemd/system/node-exporter.service
```

Configure the grok-exporter.service. Reference file location - `/cray-boot-monitoring/configuration/Grok-exporter/`

For the systemd changes to take effect, run the following command:

```bash
sudo systemctl daemon-reload
```

Now, start the grok-exporter service with the following command:

```bash
sudo systemctl start grok-exporter.service
```

### Adding Grok Exporter to Prometheus

Configure Prometheus so that it collects metrics from the computer. Then add the computer where we’ve installed Grok Exporter as a target on Prometheus. Reference file location - `/cray-boot-monitoring/configuration/Grok-exporter/`.

For the changes to take effect, restart Prometheus with the following command:

```bash
sudo systemctl restart prometheus.service
```

Now, visit the URL ` http://server_ip:9090/targets`  in web browser and see a new entry grok_exporter.


## Installing Grafana:

### Steps:

Install the grafana package:

```bash
zypper in grafana
```

Enable the Grafana service:

```bash
systemctl enable --now grafana-server
```

Grafana settings are configured in `/etc/grafana/grafana.ini` and navigate to port 3000 in your browser.

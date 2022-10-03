This is my current setup for the Raspberry Pi media server.

Docker Compose configuration which runs [Jellyfin], [Radarr], [Sonarr], [Bazarr], [Prowlarr] and [Deluge] together. In addition, it includes [Heimdall] for convenient dashboard and [Grafana] with [Prometheus] and [Node exporter] for the host monitoring.

Directories defined in the environment file (see `.env.example`) must be created in advance.

I'm currently running this on [Raspberry Pi 4 Model B] (8GB RAM).

Be aware that media using [HEVC/H.265] codec can cause issues because decoding it in real time is really CPU heavy and Pi cannot really handle it. In addition, the current setup does not take advantage of hard links and is using double disk space for downloaded media and for media it is seeding.

Possible additions in the future:
- Reverse proxy with TLS and domains
- Run Grafana on a separate machine
- Run Jellyfin on a separate machine to handle H.265
- Use hard links to save disk space

[Jellyfin]: https://github.com/jellyfin/jellyfin
[Radarr]: https://github.com/Radarr/Radarr
[Sonarr]: https://github.com/Sonarr/Sonarr
[Bazarr]: https://github.com/morpheus65535/bazarr
[Prowlarr]: https://github.com/Prowlarr/Prowlarr
[Deluge]: https://github.com/deluge-torrent/deluge
[Heimdall]: https://github.com/linuxserver/Heimdall
[Grafana]: https://github.com/grafana/grafana
[Prometheus]: https://github.com/prometheus/prometheus
[Node exporter]: https://github.com/prometheus/node_exporter
[Raspberry Pi 4 Model B]: https://www.raspberrypi.com/products/raspberry-pi-4-model-b/specifications/
[HEVC/H.265]: https://en.wikipedia.org/wiki/High_Efficiency_Video_Coding

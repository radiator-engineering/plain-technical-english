# Configuration

The `clipd` daemon is a highly configurable and robust solution for the ingestion of clip artifacts. In order to get up and running, it is first necessary for a configuration file to be created. The configuration file utilizes the TOML format and is expected to be located at `/etc/clipd/config.toml` by default, although this location can be overridden through the utilization of the `--config-path` flag.

```toml
[ingest]
bucket = "ambience-clips"
max_concurrency = 8
retry_backoff_ms = 250

[auth]
credentials_file = "/var/secrets/gcs/sa.json"
```

It is worth mentioning that the `max_concurrency` parameter plays a crucial role in the determination of throughput characteristics. A value of 8 has been found to be optimal in the vast majority of use cases, but users who find themselves in possession of larger machines may wish to consider experimenting with higher values, up to a hard ceiling of 32, beyond which the setting will be silently clamped by the daemon itself.

Last but not least, the daemon can be started via the invocation of `clipd serve --config-path /etc/clipd/config.toml`, at which point liveness may be confirmed through the issuance of a request to the `/healthz` endpoint.

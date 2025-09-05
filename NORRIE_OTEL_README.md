# Norrie OpenTelemetry Collector

This is a custom OpenTelemetry Collector built specifically for Windows Event Log collection and Elasticsearch export.

## Components Included

### Receivers
- `windowseventlog` - Collects Windows Event Logs from System, Application, and Security channels

### Processors
- `transform` - Transforms log data for ECS compatibility
- `resourcedetection` - Adds host metadata to logs

### Exporters
- `elasticsearch` - Exports logs to Elasticsearch with both ECS and OTel mapping modes

## Build Artifacts

The following Windows binaries have been built:

- `bin/norrie-otelcol_windows_amd64.exe` - Windows 64-bit (x86-64)
- `bin/norrie-otelcol_windows_arm64.exe` - Windows ARM64

## Configuration

Use the provided `norrie_otel.yml` configuration file with the collector:

```bash
norrie-otelcol_windows_amd64.exe --config norrie_otel.yml
```

## Features

- Collects Windows System, Application, and Security event logs
- Transforms logs to be compatible with Elastic Common Schema (ECS)
- Exports to Elasticsearch with both ECS and OTel mapping modes
- Adds host metadata to all log entries
- Optimized binary size by including only required components

## Requirements

- Windows 10/11 or Windows Server 2016+
- Appropriate permissions to read Windows Event Logs
- Network access to Elasticsearch endpoint
- Valid Elasticsearch API key

## Usage

1. Copy the appropriate Windows binary to your target system
2. Copy the `norrie_otel.yml` configuration file
3. Update the Elasticsearch endpoints and API key in the configuration
4. Run the collector as a service or from command line

## Configuration Notes

The configuration includes:
- Three Windows Event Log receivers (System, Application, Security)
- Transform processor for ECS compatibility
- Resource detection processor for host metadata
- Two Elasticsearch exporters (ECS and OTel mapping modes)

Make sure to update the Elasticsearch endpoints and API keys before deployment.

![Spectrum_banner.png](./Spectrum_banner_with_motto.png)

Spectrum is a fast lightweight system monitoring tool designed to collect and expose resource usage metrics from operating systems and running processes. It provides real-time visibility into CPU, memory, GPU, and power consumption with minimal overhead.

## What Spectrum Does

### Core Functionality

Spectrum monitors and tracks system resources, providing the following capabilities:

- **Process Monitoring**: Tracks CPU usage, memory consumption, and other metrics for specific processes running on the system
- **System-Wide Monitoring**: Monitors overall system resource utilization including CPU, memory, and power usage
- **GPU Monitoring**: Supports NVIDIA GPUs through NVML, collecting utilization, memory, and power metrics
- **Real-Time Metrics**: Collects and exposes metrics at configurable intervals with minimal system impact

### Data Exposure

Spectrum exposes monitoring data through multiple interfaces:

- **REST API**: HTTP-based API for querying metrics, starting/stopping traces, and retrieving system information
- **NATS Messaging**: Event-driven architecture using NATS for asynchronous metric delivery
- **JSON Format**: All data is returned in JSON format, making it easy to integrate with various clients and systems

### Observability Integration

Spectrum integrates with OpenTelemetry to provide:

- **Distributed Tracing**: Traces API requests down to background processes with timing and event details
- **Log Aggregation**: Exports logs to console, files, and OpenTelemetry collectors
- **Metrics Export**: Periodically sends collected metrics to OpenTelemetry-compatible backends

## Architecture Overview

Spectrum is designed as a background service that runs on the same machine as the processes or system you want to monitor. It exposes a programmable interface that allows users to:

1. Start tracing specific processes or system-wide metrics
2. Query current and historical metric data
3. Configure collection intervals and reporting parameters
4. Receive notifications when thresholds are exceeded

### Configuration Management

The application supports flexible configuration through:

- Command-line arguments for runtime overrides
- Environment variables for deployment settings
- YAML configuration files for persistent settings

Configuration options include:
- Messaging service URL (HTTP or NATS)
- Log level selection
- OpenTelemetry enablement and collector endpoint

## Use Cases

Spectrum is suitable for:

- **Performance Debugging**: Identify resource bottlenecks in applications
- **System Diagnostics**: Understand system resource consumption patterns
- **Monitoring Dashboards**: Feed data into visualization tools like Grafana
- **Alerting Systems**: Trigger alerts based on resource threshold violations
- **DevOps Monitoring**: Monitor containerized or scheduled workloads

## Platform Support

- **macOS**: Full support for process and system metrics
- **Linux**: Full support including NVIDIA GPU monitoring via NVML

## Getting Started

Spectrum can be configured and run in minutes:

1. Build the application using CMake
2. Configure the messaging interface (HTTP or NATS)
3. Optionally enable OpenTelemetry for external observability
4. Start the service and begin querying metrics via API or NATS

## Documentation

- **API Documentation**: REST endpoints for all operations
- **NATS Topics**: Event-driven interface following API patterns
- **Configuration Guide**: Detailed configuration options and precedence rules

## Dependencies

Spectrum uses standard, well-established libraries and frameworks to ensure reliability and maintainability. Key dependencies include:
- Modern C++ compiler (GCC/Clang)
- CMake build system
- Spdlog for logging
- OpenTelemetry for observability
- yaml-cpp for configuration
- gRPC for internal communication

---

Spectrum is developed with a focus on performance, reliability, and ease of integration. Its lightweight nature makes it ideal for both development environments and production deployments where system visibility is critical.

# OpenTelemetry Observability Backends

Based on examples from [`open-telemetry/opentelemetry-collector-contrib`](https://github.com/open-telemetry/opentelemetry-collector-contrib/tree/main/examples/demo).

- Opentelemetry Collector ==>
- Zipkin at http://0.0.0.0:9411
- Prometheus at http://0.0.0.0:9090
- 



```mermaid
graph LR
    subgraph Docker
        subgraph otelcol_network
            otelcol
            otlp
            file
            logging
            prometheus
            debug
            zipkin
        end
    end

    otelcol[otelcol:latest]
    otlp[otlp receiver]
    file[file exporter]
    logging[logging exporter]
    prometheus[prometheus exporter]
    debug[debug exporter]
    zipkin[zipkin exporter]

    otelcol -- otlp receiver --> otlp
    otelcol -- file exporter --> file
    otelcol -- logging exporter --> logging
    otelcol -- prometheus exporter --> prometheus
    otelcol -- debug exporter --> debug
    otelcol -- zipkin exporter --> zipkin
```
# Logging

```/bin/bash
kubectl create ns log
```

## Elasticsearch

Add the Elastic Helm charts repo:

```/bin/bash
helm repo add elastic https://helm.elastic.
```

Install Elasticsearch:

```/bin/bash
helm upgrade -i elasticsearch elastic/elasticsearch -f elasticsearch_override_values.yaml -n log
```

## Kibana

```/bin/bash
helm upgrade -i kibana elastic/kibana -f kibana_override_values.yaml -n log
```

## Logstash

```/bin/bash
helm upgrade -i logstash elastic/logstash -f logstash_override_values.yaml -n log
```

## Fluent Bit

```/bin/bash
helm repo add fluent https://fluent.github.io/helm-charts
helm upgrade -i fluent-bit  fluent/fluent-bit -f fluentbit_override_values.yaml -n log
```

## Refer

- [ELK Stack in Kubernetes using Helm](https://medium.com/kocsistem/elk-stack-in-kubernetes-using-helm-52398564f7fc)

- [Using Logstash with Kafka](https://itnext.io/using-logstash-with-kafka-c1e2f32af2eb)

- [How to configure Fluent Bit to collect logs for your K8s cluster](https://isitobservable.io/observability/kubernetes/how-to-configure-fluent-bit-to-collect-logs-for-your-k8s-cluster)

- https://docs.fluentbit.io/tutorials/ship_to/logstash
- https://docs.fluentbit.io/manual/installation/kubernetes 
- https://github.com/elastic/helm-charts/tree/main/logstash
# Kubernetes helm chart for izac

**Contains helm chart and deployment files for izac**

The [Confluent Platform Helm charts](https://github.com/confluentinc/cp-helm-charts) enable you to deploy Confluent Platform services on Kubernetes for development, test, and proof of concept environments.

## Installing Charts

```
helm repo add confluentinc https://confluentinc.github.io/cp-helm-charts/
helm repo update
```

## Documentation

The Confluent Helm Chart documentation is located at [docs.confluent.io](https://docs.confluent.io/current/quickstart/cp-helm-charts/docs/index.html).


## Contributing

We welcome any contributions:

- Report all enhancements, bugs, and tasks as [GitHub issues](https://github.com/confluentinc/cp-helm-charts/issues)
- Provide fixes or enhancements by opening pull requests in GitHub

## Thanks

Huge thanks to:

- [Kafka helm chart](https://github.com/kubernetes/charts/tree/master/incubator/kafka)
- [ZooKeeper helm chart](https://github.com/kubernetes/charts/tree/master/incubator/zookeeper)
- [Schema Registry helm chart](https://github.com/kubernetes/charts/tree/master/incubator/schema-registry)
- [kubernetes-kafka](https://github.com/Yolean/kubernetes-kafka)
- [docker-kafka](https://github.com/solsson/dockerfiles)
# gke-test


gcloud compute firewall-rules create myservice --allow tcp:30000-32767


gcloud compute instances list


gcloud container clusters resize standard-cluster-1 --num-nodes=1 --zone us-central1-a

curl -X POST "http://34.69.86.10:32074/events/profile/consumerOffsetsTest3" -H "accept: application/json" -H "Content-Type: application/json" -d "{ \"dimensions\": [ \"consumerGroup\", \"topic\", \"partition\", \"offset\", \"lag\"], \"segmentGranularity\": \"hour\", \"timestampColumn\": \"time\", \"timestampFormat\": \"millis\"}"
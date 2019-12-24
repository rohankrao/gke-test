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

helm install --name druid incubator/druid --set zkHosts=izac-cp-zookeeper-headless:2181 --set zookeeper.enabled=false --set historical.serviceType=NodePort --set middleManager.serviceType=NodePort --set broker.serviceType=NodePort --set overlord.serviceType=NodePort --set coordinator.serviceType=NodePort --set image.repository=apache/incubator-druid --set image.tag=0.16.0-incubating --set env.druid_zk_service_host=izac-cp-zookeeper-headless:2181 --set env.druid_metadata_storage_host=izac-postgresql-headless --set env.druid_metadata_storage_type=postgresql --set env.druid_metadata_storage_connector_connectURI=jdbc:postgresql://izac-postgresql-headless:5432/druid --set env.druid_metadata_storage_connector_user=druid --set env.druid_metadata_storage_connector_password=FoolishPassword --set druid_extensions_loadList={postgresql-metadata-storage, druid-kafka-indexing-service, druid-avro-extensions}

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


gcloud compute firewall-rules create myservice --allow tcp:30547,tcp:31390,tcp:31701,tcp:30523,tcp:31533


gcloud compute instances list

# Kafka Lab with Spring Boot

This project is a Spring Boot application designed to demonstrate the integration of Spring Boot with Apache Kafka, along with observability features using OpenTelemetry. 

---

## **🚀 Usage**

### 1️⃣ Start Minikube

- To start Minikube with the **VirtualBox driver**, allocate **12GB of RAM and 4 CPUs**:
```bash
minikube start --driver=virtualbox --memory=12288 --cpus=4
```

### 2️⃣ Create Observability Stack

```bash
kubectl create ns monitor-dev
helm install elasticsearch elastic/elasticsearch -f specs/helm/elasticsearch-values.yaml -n monitor-dev
helm install kibana elastic/kibana -f specs/helm/kibana-values.yaml -n monitor-dev
helm install otel-collector open-telemetry/opentelemetry-collector -f specs/helm/otel-collector.yaml -n monitor-dev
```

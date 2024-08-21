
# Project Setup Instructions

## Step 1: Clone the GitHub Repository

```bash
git clone <your-repo-url>
cd <your-repo-directory>
```

## Step 2: Check the Installation

Ensure the following tools are installed on your system:

1. Docker
2. Minikube
3. Kubectl

## Step 3: Start Minikube

```bash
minikube start
```

## Step 4: Create a Namespace for Fluentd

```bash
kubectl create ns fluentd
```

## Step 5: Apply Fluentd ConfigMap

```bash
kubectl apply -f fluentd-configmap.yaml
```

## Step 6: Apply Fluentd RBAC Configuration

```bash
kubectl apply -f fluentd-rbac.yaml
```

## Step 7: Deploy Fluentd

```bash
kubectl apply -f fluentd.yaml
```

## Step 8: Verify Pods and Services for Fluentd

Check if the Fluentd pods and services are running:

```bash
kubectl get pods -n fluentd
kubectl get svc -n fluentd
```

> **Note:** Ensure that both pods and services are up and running.

## Step 9: Deploy Elasticsearch Demo

```bash
kubectl apply -f elastic-demo.yaml
```

## Step 10: Deploy Kibana Demo

```bash
kubectl apply -f kibana-demo.yaml
```

## Step 11: Verify Pods and Services

Check if the pods and services are running:

```bash
kubectl get pods
kubectl get svc
```

> **Note:** Ensure that all pods and services are running.

## Step 12: Change the Kibana Service Type to NodePort

Edit the Kibana service:

```bash
kubectl edit service kibana
```

Change the field:

```yaml
type: ClusterIP
```

to:

```yaml
type: NodePort
```

## Step 13: Access Kibana

Get the access URL for Kibana:

```bash
minikube service kibana --url
```

## Step 14: Open Kibana in Your Browser

Copy the URL from the previous command and paste it into your browser to access Kibana.

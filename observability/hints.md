Install Cloud Watch Agent
https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/install-CloudWatch-Agent-commandline-fleet.html

install CloudWatch agent:
> sudo yum install amazon-cloudwatch-agent
start CloudWatch service:
> sudo /opt/aws/amazon-cloudwatch-agent/bin/amazon-cloudwatch-agent-ctl -a start

Install Promethus
https://sysdig.com/blog/kubernetes-monitoring-prometheus/

Configure the helm repo
> helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
> helm repo add stable https://kubernetes-charts.storage.googleapis.com/
> helm repo update

Install Prometheus
> helm install prometheus prometheus-community/prometheus -f ~/k8s-lab-manifests/observability/prometheus-values.yaml -n observability
-- values file overrides need for PV's and uses local storage for Prometheus server and Alert Manager

Create Ingress for Prometheus Server
> kubectl create -f ~/k8s-lab-manifests/observability/prometheus-ingress-definition.yaml -n observability
-- Ingress rule exposes the service via the NLB
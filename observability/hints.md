Install Cloud Watch Agent
https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/install-CloudWatch-Agent-commandline-fleet.html

install CloudWatch agent:
> sudo yum install amazon-cloudwatch-agent
start CloudWatch service:
> sudo /opt/aws/amazon-cloudwatch-agent/bin/amazon-cloudwatch-agent-ctl -a start
check logs
> sudo yum install amazon-cloudwatch-agent

Install Promethus and Grafana
https://sysdig.com/blog/kubernetes-monitoring-prometheus/

Configure the helm repo
> helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
> helm repo add stable https://kubernetes-charts.storage.googleapis.com/
> helm repo update

Install Prometheus
> helm install prometheus prometheus-community/prometheus -f values.yaml -n observability

Create Ingress for Prometheus Server
> kubectl create -f ~/k8s-lab-manifests/observability/prometheus-ingress-definition.yaml -n observability
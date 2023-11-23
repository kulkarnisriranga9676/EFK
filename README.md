# EFK
EFK Setup for Kubernetes
Use the deployment files to install Elasticsearch and Kibana.
use the fluentd deployment file with configmap which helps to customzie the fluentd config file like matching pattern, index name, formatting the logs, exluding the containers specific not to log and even namespace not to log

commands 

kubectl apply -f es.yaml
kubectl apply -f fluendt.yaml
add container names or namespace in the below pattern to add to exclude list
  to exclude a container
      exclude_path ["/var/log/containers/fluent*"]
  to exclude a namespace
      exclude_path ["/var/log/containers/*_testing_*-*.log] for reference {"/var/log/containers/*_testing_*-*.log}

kubectl rollout restart daemonset <> -n namespace



asd

# Overview
This project demonstrates the deployment of Jenkins inside a Kubernetes cluster, exposed securely via ngrok, and integrated with both GitHub and Gitea for CI/CD using webhooks and Jenkinsfile.


1. Fork this repository
2. Configure webhooks:
   - GitHub: `http://<NGROK-URL>/github-webhook/`
   - Gitea: `http://jenkins.jenkins.svc.cluster.local:8080/gitea-webhook/`


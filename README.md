# Jenkins Pipeline Setup
1. Fork this repository
2. Configure webhooks:
   - GitHub: `http://<NGROK-URL>/github-webhook/`
   - Gitea: `http://jenkins.jenkins.svc.cluster.local:8080/gitea-webhook/`
3. Jenkinsfile stages:
   - Build with Python 3
   - Test with pytest
   - Deliver with PyInstaller
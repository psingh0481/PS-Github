# Overview
This project demonstrates the deployment of Jenkins inside a Kubernetes cluster, exposed securely via ngrok, and integrated with both GitHub and Gitea for CI/CD using webhooks and Jenkinsfile.

## This document explains how to set up your repository and configure GitHub to trigger a Jenkins pipeline using a Jenkinsfile. The Jenkins job is exposed through ngrok, making it accessible externally. This is used for the 2nd part of the assignment.

## Steps
1. Fork this repository from https://github.com/jenkins-docs/simple-python-pyinstaller-app 

2. Push your repository to GitHub.

3. Configure GitHub webhooks to trigger Jenkins jobs through an ngrok ingress.

Jenkins Setup: A running Jenkins instance configured to accept pipeline jobs.

Ngrok Account: To tunnel the Jenkins service externally.

GitHub Account: To host the repository containing the Jenkinsfile.

4. Add the Jenkinsfile from the provided article or modify it to suit your pipeline needs.

5. Jenkinsfile Configuration
Pipeline Definition: Ensure your Jenkinsfile defines all stages (e.g., build, test, deploy) required by your assignment.

Environment Variables: Set up any environment variables or credentials if needed.

Testing: Locally test your Jenkinsfile (if using a pipeline simulation tool) to ensure it runs correctly.

6. Push to GitHub
Initialize your local repository if not already done:
7. Expose your Jenkins instance (e.g., if Jenkins is running on port 3002)
8. Update Jenkins Configuration: Within Jenkins, confirm that the Jenkins URL under Manage Jenkins → Configure System matches the ngrok URL.
9. Configure GitHub Webhook: In your GitHub repository settings, go to Webhooks and add a new webhook.
10. Triiger Pipeline: Check the Jenkins pipeline build

11. Troubleshooting Tips
Webhook Test: Use the “Test webhook” feature on GitHub to check connectivity.
Ngrok Logs: Monitor ngrok logs for any errors related to tunnelling.
Jenkins Log: Check Jenkins system logs for pipeline trigger issues.
Network Restrictions: Confirm no firewall or network settings are blocking the ngrok connection.

## Author
Priya

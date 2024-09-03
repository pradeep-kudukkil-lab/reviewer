GitHub Actions Workflows
----
This repository contains two GitHub Actions workflows to manage and deploy changes to the pradeepprod branch based on pull request reviews.

Workflows
--
1. Check Who Approved
This workflow is triggered whenever a pull request review is submitted. It checks if the pull request was approved by a specific user before allowing the deployment to proceed.
Workflow File: .github/workflows/prreview.yml

Purpose:
Ensure that only the specified approver (ashiqpradeepsolutions) can approve the deployment.
This workflow will fail if the approval is not from the specified user, preventing further actions.

2. Deploy to Production
This workflow is triggered when a pull request to the pradeepprod branch is closed (i.e., merged). It reads input from a file and proceeds with the deployment if the specified approver has approved the PR.
Workflow File: .github/workflows/production-deployment.yml

Purpose:
Deploy changes to the pradeepprod branch after ensuring the PR has been merged.
Reads additional information from an input.txt file and proceeds with deployment.
Usage
Branch Protection Rules: Add the Check Who Approved workflow as a required status check in the branch protection rules for pradeepprod to ensure that only approved changes can be deployed.

Deploy Workflow: The deployment workflow will automatically trigger after a successful merge to the pradeepprod branch, provided the required approval was obtained.

Notes
Make sure to replace ashiqpradeepsolutions with the correct GitHub username for your specific use case.
The input.txt file should be structured with key-value pairs like: 

name: YourName
age: 30


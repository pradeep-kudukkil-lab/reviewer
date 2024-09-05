Workflows Overview
--
1. Check Who Approved
Purpose: Ensures that only the specified user (ashiqpradeepsolutions) can approve deployments.
Trigger: Runs when a pull request review is submitted.
Key Steps:
Verifies if the pull request was approved.
Checks if the approver matches ashiqpradeepsolutions.
Fails the workflow if the approval is from anyone else.
Note: A branch protection rule is already in place for the pradeepprod branch, requiring the Check Who Approved workflow to pass before any merge can occur. This ensures that deployments are only triggered after approval by the specified user.

2. Deploy to Production
Purpose: Deploys to the production environment after the pull request is approved and merged into the pradeepprod branch.
Trigger: Runs when a pull request to the pradeepprod branch is merged.
Key Steps:
Reads deployment details from the prod_input.txt file.
Echoes the approver’s name and additional information (like age).
Proceeds with the production deployment.

3. Deploy to Development
Purpose: Deploys to the development environment following approval and merge into the pradeepprod branch.
Trigger: Runs when a pull request to the pradeepprod branch is merged.
Key Steps:
Reads deployment details from the dev_input.txt file.
Echoes the approver’s name and additional information (like age).
Proceeds with the development deployment.


Additional Information
The pradeepprod branch is protected by a branch protection rule that enforces the Check Who Approved workflow as a required status check. This ensures that deployments only occur if the pull request is approved by ashiqpradeepsolutions.
The Deploy to Production and Deploy to Development workflows are triggered only after the pradeepprod branch has been successfully merged and the specified approval conditions are met.

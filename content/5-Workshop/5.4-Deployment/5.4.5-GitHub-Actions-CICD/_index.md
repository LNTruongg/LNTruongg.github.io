---
title: "CI/CD with GitHub Actions"
date: 2026-11-27
weight: 5
chapter: false
pre: " <b> 5.4.5. </b> "
---

#### 1. Create the CI workflow

GitHub Actions runs backend tests, builds the frontend and validates Docker builds before deployment.

1. Download the [CI workflow](./attachments/deploy-aws.yml.txt). In your repository, create `.github/workflows/` and save the contents as `deploy-aws.yml`.
2. Check that `on.push.branches` matches your branch. Check that `backend/requirements.txt`, `backend/tests/`, `frontend/package-lock.json` and both Dockerfiles exist in the repository.
3. Commit and push the workflow to your repository. Open **Actions**, select CoupleLife AI — CI, or choose Run workflow to run it manually.

4. Open the run and select the CI job to inspect pytest, frontend build and Docker build results. Under Artifacts, download `frontend-dist` if you need to inspect the bundle.

![Run 12: CI success, CD skipped](./image_5.4.5/02-ci-run-12.png)

The illustration shows a successful CI run with CD skipped. The attached workflow runs CI only, grants no AWS deployment permissions and creates no AWS resources. Inspect the logs for errors before releasing.

#### 2. Deploy a new version

After CI passes, use section 5.4.1 to build and push the images and section 5.4.2 to deploy EC2. For an image update, create a new Launch Template version with the new tag and select it in the ASG. Check migration compatibility and back up data before updating. Open ASG → Instance refresh → Start instance refresh, configure gradual replacement and check target health as in section 5.4.3; avoid taking both targets down together. If necessary, restore a previous version that is compatible with the database schema. Update the frontend using section 5.4.4 once the API is ready.

To extend this to automated CD, configure a GitHub OIDC role restricted to the repository/environment and necessary ECR, S3, CloudFront and SSM permissions. Use environment protection and check each SSM command, image tag and health check before release. This lab uses CI and manual deployment so you can control each step.

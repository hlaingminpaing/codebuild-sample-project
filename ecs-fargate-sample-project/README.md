# ECS Fargate App (Node.js + Docker + CodeBuild)

## 📦 Project Structure
- `app.js`: Express app
- `Dockerfile`: Container build
- `buildspec.yml`: AWS CodeBuild instructions

## 🚀 Setup & Deploy

1. Push repo to GitHub.
2. Create ECR repository `ecs-fargate-app`.
3. Create ECS Cluster and Service using Fargate with a load balancer.
4. Create CodeBuild project:
   - Source: GitHub
   - Privileged mode: ✅ (to build Docker)
   - Environment variables:
     - `AWS_ACCOUNT_ID`, `AWS_REGION`
   - Artifacts: `imagedefinitions.json`

5. (Optional) Use CodePipeline for CI/CD using the image artifact.

6. Access the app via Load Balancer URL.

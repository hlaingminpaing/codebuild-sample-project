# Node.js Lambda Function (CodeBuild)

## 📦 Project Structure
- `index.js`: Main Lambda function
- `buildspec.yml`: AWS CodeBuild instructions

## 🚀 How to Deploy

1. Push this repo to GitHub.
2. Create a Lambda function in AWS Console (e.g. "MyLambda").
3. Create a CodeBuild project:
   - Source: GitHub
   - Environment: Standard, Amazon Linux 2, Node.js 18
   - Artifact: Store `function.zip` in S3

4. (Manual test) Deploy with CLI:
   ```bash
   aws lambda update-function-code \
     --function-name MyLambda \
     --zip-file fileb://function.zip

## 🧩 CodeDeploy Setup

- Create Lambda alias `live`
- Create CodeDeploy App (type: Lambda)
- Add Deployment Group targeting `live` alias
- Add to CodePipeline to deploy `function.zip`

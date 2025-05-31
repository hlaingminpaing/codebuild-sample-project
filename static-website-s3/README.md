# Static Website to S3

## 📦 Project Structure
- `index.html`: Website homepage
- `buildspec.yml`: Deploys to S3

## 🚀 Setup & Deploy

1. Create a public S3 bucket (e.g. `my-static-site-bucket`) and enable static website hosting.
2. Push this repo to GitHub.
3. Create a CodeBuild project:
   - Source: GitHub
   - Environment: Amazon Linux 2 standard
   - IAM Role must allow `s3:PutObject` and `s3:DeleteObject`
4. Add environment variable:
   - `S3_BUCKET=my-static-site-bucket`
5. Update `buildspec.yml` if using env var:
   ```yaml
   - aws s3 sync . s3://$S3_BUCKET/ --delete

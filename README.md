# GitHub Actions Deployment Workflow

Project from: [https://roadmap.sh/projects/github-actions-deployment-workflow](https://roadmap.sh/projects/github-actions-deployment-workflow)

The **GitHub Actions Deployment Workflow** project demonstrates how to configure a streamlined CI/CD pipeline using GitHub Actions. It automates testing, building, and deploying applications to environments such as GitHub Pages.

## Features

- Automatically deploys changes to GitHub Pages on push to the `website` branch.
- Includes optional testing and validation steps for robust CI/CD.
- Supports dynamic branch management and merges to the `main` branch post-deployment.

## Usage

### Workflow Overview
- **Trigger**:
  - Executes on `push` events to the `website` branch.
- **Jobs**:
  1. **Deploy**:
     - Deploys site files to the `gh-pages` branch.
  2. **Merge**:
     - Optionally merges the `website` branch into `main` post-deployment.

### Example Workflow Execution
1. Push changes to the `website` branch:
   ```bash
   git checkout website
   git add .
   git commit -m "Update website content"
   git push origin website
   ```
2. The workflow will:
   - Build and deploy your changes to GitHub Pages.
   - Optionally merge the branch into `main` if configured.

### Accessing the Deployed Site
- Deployed sites are available at:
  ```
  https://<your-username>.github.io/<your-repo>
  ```

## Development Environment

- **Tools Used**:
  - GitHub Actions for automation.
  - `actions/checkout@v3` for repository management.
  - `peaceiris/actions-gh-pages@v3` for GitHub Pages deployment.
- **Environment**:
  - Configured on GitHub.
  - Supports Node.js for advanced builds.

## Improvements
- Add support for more deployment targets, such as S3 or Firebase.
- Enable testing pipelines with `npm test` for enhanced validation.
- Introduce notifications for workflow completion (e.g., Slack or email alerts).
- Enhance security by using environment-specific secrets.

## Example Workflow Configuration

```yaml
name: CI/CD Pipeline

on:
  push:
    branches:
      - website

jobs:
  deploy:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout repository
        uses: actions/checkout@v3

      - name: Deploy to GitHub Pages
        uses: peaceiris/actions-gh-pages@v3
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: ./build

  merge:
    needs: deploy
    runs-on: ubuntu-latest

    steps:
      - name: Checkout repository
        uses: actions/checkout@v3
        with:
          ref: website

      - name: Merge into main
        run: |
          git checkout main || git checkout -b main
          git merge website --no-ff
          git push origin main
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

## Conclusion

The **GitHub Actions Deployment Workflow** simplifies CI/CD for projects by automating deployment and branch management. It’s a robust solution for maintaining an efficient deployment process, whether for personal projects or professional use.

The [project link](https://roadmap.sh/projects/github-actions-deployment-workflow).

Thanks to [https://roadmap.sh](https://roadmap.sh/).

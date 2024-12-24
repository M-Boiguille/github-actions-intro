# GitHub Actions Deployment Workflow

Project from: [https://roadmap.sh/projects/github-actions-deployment-workflow](https://roadmap.sh/projects/github-actions-deployment-workflow)

The **GitHub Actions Deployment Workflow** project demonstrates how to configure a streamlined CI/CD pipeline using GitHub Actions. It automates testing, building, and deploying applications to environments such as GitHub Pages.

## Features

- Automatically deploys changes to GitHub Pages on push on the `index.html` file.
- Includes optional testing and validation steps for robust CI/CD.

## Usage

### Workflow Overview
- **Trigger**:
  - Executes on `push` events to the 'index.html' in the `main` branch.
- **Jobs**:
  1. **Deploy**:
     - Deploys site files to the `gh-pages` branch.

### Example Workflow Execution
1. Push changes on the `index.html` file:
   ```bash
   git add .
   git commit -m "Update website content"
   ```
2. The workflow will:
   - Build and deploy your changes to GitHub Pages.
   - Test the html before deploying.

### Accessing the Deployed Site
- Deployed sites are available at:
  ```
    https://github.io/M-Boiguille/github-actions-intro.
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
- Enable testing pipelines with `npm test` for enhanced validation.
- Introduce notifications for workflow completion (e.g., Slack or email alerts).
- Enhance security by using environment-specific secrets.

## Conclusion

The **GitHub Actions Deployment Workflow** simplifies CI/CD for projects by automating deployment and branch management. It’s a robust solution for maintaining an efficient deployment process, whether for personal projects or professional use.

The [project link](https://roadmap.sh/projects/github-actions-deployment-workflow).

Thanks to [https://roadmap.sh](https://roadmap.sh/).

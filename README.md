# Awesome Action Starter

Awesome cross-platform TypeScript action starter that can be run on GitHub Actions, GitLab CI, or Bitbucket Pipelines.

[Create new repository from this template](https://github.com/new?template_name=awesome-action-starter&template_owner=mathio).

Read more about [Building Cross-Platform CI/CD Actions with Docker](https://dev.to/mathio/building-cross-platform-cicd-actions-with-docker-3c9o).

If you like this, _start this repo ⭐_ and [follow me 🐦](https://twitter.com/mathio28)

## Usage

### GitHub Actions

```yaml
name: Run Hello World
on: [push]

jobs:
  hello:
    runs-on: ubuntu-latest
    steps:
      - uses: mathio/hello-world-action@main
```

### GitLab CI

```yaml
hello:
  image: ghcr.io/mathio/hello-world-action:latest
  script:
    - echo "Done"
  rules:
    - if: $CI_PIPELINE_SOURCE == "push" && $CI_COMMIT_BRANCH == "main"
```

### Bitbucket Pipelines

```yaml
pipelines:
  branches:
    main:
      - step:
          image: ghcr.io/mathio/hello-world-action:latest
          script:
            - echo "Done"
```

## Development

1. Install pnpm (if not already installed):

   ```bash
   npm install -g pnpm
   ```

2. Install dependencies:

   ```bash
   pnpm install
   ```

3. Build the TypeScript code:

   ```bash
   pnpm build
   ```

4. Run locally:
   ```bash
   node build/index.js
   ```

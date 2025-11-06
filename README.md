# arm-ultralytics-env-server

This repository is used to build a development environment for ultralytics on ARM devices. It includes necessary dependencies and configurations to ensure smooth operation of ultralytics on ARM architecture. And publish the environment as a Docker image to github container registry for easy access and deployment.

## CI/CD Pipeline

This project uses GitHub Actions to automatically build and publish Docker images to GitHub Container Registry (ghcr.io).

### Workflow Features

- **Automatic Build**: Triggers on push to `main`/`master` branch, version tags, or pull requests
- **ARM64 Architecture**: Builds specifically for `linux/arm64` (aarch64) platform
- **Container Registry**: Automatically publishes to GitHub Container Registry
- **Smart Tagging**: 
  - `latest` tag for the default branch
  - Branch name tags for feature branches
  - Semantic version tags (e.g., `v1.0.0`, `1.0`, `1`) when pushing git tags
- **Build Cache**: Utilizes GitHub Actions cache to speed up subsequent builds

### Using the Docker Image

Pull the latest image:
```bash
docker pull ghcr.io/<username>/arm-ultralytics-env-server:latest
```

Run the container:
```bash
docker run -it ghcr.io/<username>/arm-ultralytics-env-server:latest
```

### Creating a Release

To publish a versioned release:
```bash
git tag v1.0.0
git push origin v1.0.0
```

This will automatically build and publish the image with tags: `v1.0.0`, `1.0`, `1`, and `latest`.

## References

- [GitHub Actions Documentation](https://docs.github.com/en/actions)
- [Docker Build and Push Action](https://github.com/docker/build-push-action)
- [GitHub Container Registry](https://docs.github.com/en/packages/working-with-a-github-packages-registry/working-with-the-container-registry)


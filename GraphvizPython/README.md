# Build Container with Buildx Builder

For parallel build with multi-architecture support, it is possible to use Buildx builder:

Sources:
- https://www.macstadium.com/blog/building-docker-images-on-apple-silicon-with-buildx
- https://www.docker.com/blog/multi-arch-images/

```bash
docker buildx build --platform linux/amd64,linux/arm64,linux/arm/v7 --builder mybuilder -t julianbuecher/python-graphviz:latest --push .
```
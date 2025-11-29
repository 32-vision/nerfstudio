# Docker Image with COLMAP 3.8

This branch (`colmap-3.8`) provides a Dockerfile modified to install **COLMAP 3.8** for use with the nerfstudio environment.

---

## 1. Pull This Branch

```bash
git checkout colmap-3.8
git pull origin colmap-3.8
```

---

## 2. Build the Docker Image

Build the image using the Dockerfile included in this branch.
The image name (`nerfstudio-75`) below is **just an example** — feel free to use any name you prefer.

```bash
docker build \
  --build-arg CUDA_ARCHITECTURES=75 \
  --tag nerfstudio-75 \
  --file Dockerfile .
```

- `--build-arg CUDA_ARCHITECTURES=75`: Set the target CUDA architecture
- `--tag nerfstudio-75`: Tag name for the built image (example / arbitrary)

---

## 3. Verify COLMAP Version Inside the Container

Check that COLMAP 3.8 is correctly installed:

```bash
docker run --rm --gpus all nerfstudio-75 colmap -v
```

You should see output indicating COLMAP 3.8.

---

## Notes
- GPU support maybe requires Docker with the NVIDIA Container Toolkit.
- Adjust `CUDA_ARCHITECTURES` as needed for your hardware.

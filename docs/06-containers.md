## Section 6: Reproducibility via containers (Docker & Singularity)
Containers encapsulate dependencies, libraries, and operating system assets, assuring exact execution across different platforms.

### 6.1 Building and running docker containers Local / Cloud

```bash
# Build Docker image from Dockerfile
docker build -t bio_pipeline:v1.0 .

# Execute container interactively mapping local data folder
docker run --rm -v $(pwd)/data:/data -it bio_pipeline:v1.0 bash
```

### 6.2 Converting docker to singularity/apptainer for HPC
Convert Docker images to Singularity Image Files (`.sif`):

```bash
# Build Singularity image directly from Docker Hub
singularity build bio_pipeline.sif docker://username/bio_pipeline:v1.0

# Execute command inside Singularity container on cluster
singularity exec bio_pipeline.sif python src/main.py
```

> [!WARNING]
> Most institutional HPC clusters prohibit Docker due to root privilege restrictions.
## Section 7: Scalable workflow management (Snakemake & Nextflow)
Workflow engines structure execution as Directed Acyclic Graphs (DAGs), enabling automated parallelism, failure recovery, and cross-platform portability.

### 7.1 Snakemake execution example
A typical Snakefile coordinates tasks seamlessly:

```bash
# Dry run to preview execution steps
snakemake -n

# Run pipeline utilizing available local CPU cores
snakemake --cores 8 --use-conda
```

### 7.2 Core principles for computational biology pipelines
- Modularity: Isolate Quality Control (FastQC/Trimmomatic), Mapping (STAR/HISAT2), Quantification (featureCounts), and Downstream Analysis (DESeq2/PyWGCNA) into independent rules.
- Portability: Combine Snakemake/Nextflow with Conda or Singularity containers to allow identical execution across laptops, HPC clusters, and cloud environments (AWS/GCP).

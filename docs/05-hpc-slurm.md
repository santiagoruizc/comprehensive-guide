## Section 5: High-Performance Computing (HPC) & Slurm workloads
Guidance for submitting multi-threaded and memory-intensive computational jobs to institutional clusters managed by Slurm.

### 5.1 Key slurm commands
- `squeue -u $USER` -> Display active and pending jobs for user.
- `scancel <JOB_ID>` -> Terminate a specific job task.
- `sinfo` -> Inspect node health and partition limits.

### 5.2 Production slurm batch script template (`run_pipeline.sh`)

```bash
#!/bin/bash
#SBATCH --job-name=omics_pipeline
#SBATCH --output=logs/pipeline_%j.log
#SBATCH --error=logs/pipeline_%j.err
#SBATCH --ntasks=1
#SBATCH --cpus-per-task=8
#SBATCH --mem=32G
#SBATCH --time=04:00:00
#SBATCH --partition=standard

# Fail on error
set -e

# Initialize Conda inside batch environment
source ~/anaconda3/etc/profile.d/conda.sh
conda activate bio_env

# Execute multi-threaded script using allocated Slurm cores
python src/main.py --threads $SLURM_CPUS_PER_TASK
```

Submit job to scheduler:

```bash
sbatch run_pipeline.sh
```
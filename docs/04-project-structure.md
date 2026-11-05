## Section 4: Project directory architecture & large data handling

### 4.1 Production-grade bioinformatics project layout
Adhere to a clean modular architecture separating raw inputs, processed outputs, source code, and configuration parameters:

```Plaintext
bio-project-template/
├── .gitignore               # Excluded patterns from Git tracking
├── .gitattributes           # Git LFS specifications
├── README.md                # Project documentation and reproduction guide
├── environment.yml          # Reproducible Conda environment specification
├── config/
│   └── config.yaml          # Pipeline hyperparameters and dataset paths
├── data/
│   ├── raw/                 # Immutable raw biological datasets (Git-ignored)
│   └── processed/           # Filtered, normalized, or transformed data
├── notebooks/               # Exploratory analyses (.ipynb)
├── scripts/                 # Utility Bash and Python executable scripts
├── src/                     # Core modular code, custom packages, and functions
└── results/                 # Publication-ready figures, tables, and reports
```
### 4.2 Handling large-scale biological data & Git LFS
Repositories on GitHub enforce file size caps (100 MB max per file). Raw sequence files (FASTQ, BAM, VCF) and heavy matrices must be managed via `.gitignore` or tracked explicitly with Git Large File Storage (LFS).

#### Recommended `.gitignore` Template for Omics Workflows

```Code snippet
# Raw and Intermediate Genomic/Omics Files
*.fastq
*.fastq.gz
*.fq
*.bam
*.sam
*.vcf
*.vcf.gz
*.fasta
*.fna
*.fa
*.h5
*.parquet

# R & Python Heavy Objects
*.RData
*.rds
*.pickle

# Installers and Binaries
*.sh
!scripts/*.sh

# Environments and Caches
__pycache__/
.ipynb_checkpoints/
env/
venv/
```

#### Git LFS Configuration
##### If intermediate reference tables must be versioned:

```bash
# Initialize Git LFS tracking
git lfs install

# Track specific heavy biological extensions
git lfs track "*.bam"
git lfs track "*.h5"

# Commit tracking rules
git add .gitattributes
git commit -m "build: configure Git LFS for binary data tracking"
```

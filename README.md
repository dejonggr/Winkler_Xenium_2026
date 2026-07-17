# Example project (AA_BBB)

Description of the project here. What is the project aim and what kind of scientific discovery did you do?

## Getting started

- Click 'Use this template' button > [Create a new repository](https://github.com/new?owner=BayraktarLab&template_name=project_template&template_owner=BayraktarLab) and name the Repository name with the project name.
- Make sure you selected 'Private'
- Create repository
- Clone to NFS
```bash
cd /nfs/team283/<user>/projects/
git clone https://github.com/<username>/<project_name>.git
```
- Copy directory structure to Lustre


## Directory structure

- `data` - Store raw data here (**NFS**)
- `metadata` - Store raw metadata here (**NFS**)
- `scripts` - Store scripts and notebooks here
    - Large notebooks on Lustre
    - Convert large notebooks for NFS: `jupyter nbconvert --to script <name>.ipynb`
- `figures` - Store figures here
- `results` - Store processed results here (e.g. AnnData or their annotations in CSV-format with cell- or spot-barcode as index)
- `tmp` - Store temporary files here, including:
    - model.pt files
    - LSF or pipeline (Snakemake/Nextflow) log files
    - Figures


## Branches

List branches here:

- `main` - Typically the final version of a project.
- `<name>` - Ongoing analyses, figures, or subprojects.

[Branches in a nutshell](https://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell) 🪾


## Code documentation

Key to good reproducibility is to describe your scripts and notebooks here for others to use. Make it a habit to update this for **Git Friday**.

### Example

- `scripts`
    - `preprocess_scrna.py` - "Pre-processes raw scRNA-seq data, applies quality control and writes Anndata object for downstream analysis."
    - `cell2location.py` - "Runs cell2location cell type deconvolution of scRNA-seq from `<script.py>` to paired Visium data."
    - `plot_cell2location_results.ipynb` - "Generate figure <X> to show spatial location of our cell type population of interest."
- `data`
    - `<project_name>__scRNA.h5ad` - Original raw Anndata object
- `results`
    - `<project_name>__v1__scRNA__filt_cells_filt_genes__log1pnorm_counts__QC__scVI__cell_types_lvl1.h5ad` - Processed Anndata object (v1, dd/mm/yyyy) with QC, cell/gene filtering, scVI integration and cell type annotation at level 1-resolution (see script README for details).



## Software

Provide the required software to run / reproduce results here.

- Pre-installed Farm modules

```bash
module load cellgen/<module_name>
```

- Existing Conda environments

```bash
module load cellgen/conda
conda activate <environment_name>
```

- New but reproducible (from YML file) Conda environments

```bash
module load cellgen/conda
conda env create --name <environment_name> --file=<environment_name.yml>
```

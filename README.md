# Morpheus-computation Practice
This demo assesses the performance of CEU’s Morpheus cluster and shows how parallelization boosts efficiency. By benchmarking tasks and comparing scaling methods, it highlights strengths, bottlenecks, and how parallel processing reduces computation time.

# What is Morpheus?
Morpheus is a high-performance computing (HPC) cluster used within CEU.
It provides:
- Centralised RStudio access via browser:🔗 https://morpheus.ndph.ox.ac.uk/rstudio/
- High-speed CPUs and large memory for demanding computations.
- Shared resources across researchers, ensuring reproducibility and efficiency.

# Ideal for:
- Large data analysis
- Simulation studies
- High-dimensional modelling
- Parallel computations



# System Environment Feature
| Query | R command  | Output |
|------|-----|---------|
| R version | R.version.string | R version 4.1.0 (2021-05-18) |
| R home | R.home() | /opt/R/4.1.0/lib/R |
| System | R.version.string | R version 4.1.0 (2021-05-18) |
| CPU cores | detectCores(logical=TRUE) | 64 cores |
| Total memory | grep MemTotal /proc/meminfo | e.g. 1055952692 kB ≈ 1 TB |







# Why More RAM Helps in High-Dimensional Analysis
| Scenario | Why RAM is Important | Example |
|------|-----|---------|
| 1. Reading large datasets | Data must fit in memory before analysis. If the dataset is larger than RAM, R has to use disk (slow, can crash). |Importing a 200 GB genomics matrix or population dataset directly into R. |
| 2. Running statistical models | Many algorithms (e.g., regression, PCA, mixed models) load full matrices into memory. | Running PCA on a 100 000 × 1000 matrix — needs several GB. |
| 3. Parallel computation | Each worker process needs its own memory slice. Low RAM limits how many cores you can use efficiently. | 64 cores — each needs a few GB to store its chunk of data.|
| 4. Avoiding disk bottlenecks | When RAM is insufficient, data is swapped to disk (“virtual memory”) → 10–100× slower. | Large joins or merges that spill to swap space |




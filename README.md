# drab
RNA-seq count tables, revisited

## C++ Hello World Example

This repository includes a simple C++ "Hello World" example that demonstrates:
- Building C++ code with CMake
- Managing dependencies with Conda
- Orchestrating workflows with Snakemake

### Structure

- `src/`: Contains C++ source code and CMakeLists.txt
- `env/`: Contains Conda environment specifications
- `workflow/`: Contains Snakefile for build automation

### Usage

To build and run the example using Snakemake:

```bash
cd workflow
snakemake --use-conda --cores 1
```

This will:
1. Create a conda environment with cmake and g++
2. Compile the C++ code
3. Run the executable and save output to `output/hello_output.txt`

### Manual Build

To build manually without Snakemake:

```bash
mkdir -p build
cd build
cmake ../src
cmake --build .
./hello
```

### CI/CD

This repository includes a GitHub Actions workflow that:
- Runs automatically on pull requests to main
- Can be manually triggered via workflow_dispatch
- Uses conda-incubator/setup-miniconda to set up Mambaforge
- Installs Snakemake and runs the workflow
- Verifies the output and uploads artifacts

# drab

RNA-seq count tables, revisited

### Structure

- `src/`: Contains C++ source code and CMakeLists.txt
- `env/`: Contains Conda environment specifications
- `workflow/`: Contains Snakefile for build automation

### Running with snmk

To build and run the example using Snakemake:

```bash
cd workflow
snakemake --use-conda --cores 1
```

This will:
1. Create a conda environment with cmake and g++
2. Compile the C++ code
3. Run the executable and save output to `output/hello_output.txt`

### Building `src`

To build manually without Snakemake:

```bash
mkdir -p build
cd build
cmake ../src
cmake --build .
./hello
```

### CI/CD

- `snakemake.yml` to run the workflow (serially)

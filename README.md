# phonopy-eigenvector-tblg-benchmark

```
git clone https://github.com/ExpHP/phonopy-eigenvector-tblg-benchmark
cd phonopy-eigenvector-tblg-benchmark
./bench output-name --hdf5
```

It primarily benchmarks the command

```
phonopy --readfc --hdf5 --band="0 0 0..." --band_points=100 --eigenvectors
```

Output containing profiling info will be written to `output-name-2.prof` and `output-name-3.prof`.

The first time it is run it will compute the force constants. This is not included in the benchmark results,
so it can be kept around to speed up subsequent benchmarks.

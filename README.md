# phonopy tBLG eigenvectors benchmark

```
git clone https://github.com/ExpHP/phonopy-eigenvector-tblg-benchmark
cd phonopy-eigenvector-tblg-benchmark
./bench output-name --hdf5
```

It primarily benchmarks the command

```
phonopy --readfc --hdf5 --band_points=100 --eigenvectors --dim="6 6 1" \
         --band="0 0 0 0.5 0 0 0.333333 0.333333 0 0 0 0" 
```

* Both python2 and python3 are tested.
* Output containing **profiling info** will be written to `output-name-2.prof` and `output-name-3.prof`.
* It also copies the **band.yaml** to `output-name-2.yaml` and `output-name-3.yaml`.  (This is so I can see what modifications change the output.)

The first time it is run it will compute the force constants. This is not included in the benchmark results,
so it can be kept around to speed up subsequent benchmarks.

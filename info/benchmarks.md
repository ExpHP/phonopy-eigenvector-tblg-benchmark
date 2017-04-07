| Commit                     | `np.rint` | 1st loop | 2nd loop | `solve` (1st) | `solve` (2nd) | `reduced_` `bases` arg | band.yaml MD5 | Time (total)  | Time (`get_`...) |
| ------------               | --------- | -------- | -------- | -------------------- | -------------        | ---                 | ---           | ---           | ---       |
| **[21cb9e37240d](https://github.com/ExpHP/phonopy/commit/21cb9e37240df3d8e7217c428370819424e6eead) (original)** |     **[ ]**   |   **[ ]**    | **[ ]**      |    **[ ]**               |   **[ ]**                |    **[ ]**              | **`4d89ccbf`**    |  **97s\/82s** | **86s\/70s** |
| [f72d9ffe223e](https://github.com/ExpHP/phonopy/commit/f72d9ffe223ea7d01828b4292f1da9f83a72a6b8)              |     [x]   |   [ ]    | [ ]      |    [ ]               |   [ ]                |    [ ]              | `4d89ccbf`    |  37s\/36s | 25s\/25s |
| **[ece7dd284773](https://github.com/ExpHP/phonopy/commit/ece7dd284773250151b59aa01386a88692e9bfeb) ([my PR](https://github.com/atztogo/phonopy/pull/41))** |     **[x]**   |   **[x]**    | **[ ]**      |    **[ ]**               |   **[ ]**                |    **[ ]**              | **`4d89ccbf`**    |  **23s\/22s** | **11s\/11s** |
| N\/A                       |     [x]   |   [x]    | [x]      |    [ ]               |   [ ]                |    [ ]              | `4d89ccbf`    |  22s\/22s | 10s\/10s |
| N\/A                       |     [x]   |   [x]    | [ ]      |    [x]               |   [x]                |    [ ]              | `ecde5f73`    |  26s\/27s | 14s\/16s |
| N\/A                       |     [x]   |   [x]    | [ ]      |    [ ]               |   [x]                |    [ ]              | `4d89ccbf`    |  22s\/24s | 10s\/13s |
| [7ec01046800f](https://github.com/ExpHP/phonopy/commit/7ec01046800faaca76aaa5935c9d54d8281ff258)               |     [x]   |   [x]    | [ ]      |    [ ]               |   [ ]                |    [x]              | `4d89ccbf`    |  17s\/18s | 5.5s\/6.8s |

**Notes:**

* Times are **python2 time\/python3 time**
* `[x]/[ ]` = **modification present/not present**
* All times shown here are for **a single run** (standard deviations are unknown)
* The **first two columns** correspond to the linked commits from my PR branch. 
* **"2nd loop"** replaces the second half of the function with the code I wrote in the commit message for ece7dd284773.
* **`solve` (1st/2nd)** replace each instance of `np.dot(a, np.linalg.inv(b))` with `np.linalg.solve(a.T, b.T).T`. _This actually turns out to be a pessimization!_
* **`reduced_bases` arg** makes `get_smallest_equivalent_vectors` take `reduced_bases` as an argument so that it can be precomputed.
* "band.yaml MD5" gives an idea of how faithful the optimized code is to the original.  Where the MD5s match, the produced band.yamls are _bit-by-bit identical._


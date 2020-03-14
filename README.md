The 'Ckmeans.1d.dp' R package
=================================

### Overview

The package provides fast, optimal, and reproducible univariate clustering by dynamic programming. It is practical to cluster millions of sample points with optional weights in seconds on a typical desktop computer using a single processor core.

Four types of problem including univariate $k$-means, $k$-median, $k$-segments, and multi-channel weighted $k$-means are solved with guaranteed optimality and reproducibility. The core algorithm minimizes the (weighted) sum of within-cluster distances using respective metrics. Its advantage over heuristic clustering in efficiency and accuracy is increasingly pronounced as the number of clusters $k$ increases. Weighted $k$-means can also optimally segment time series to perform peak calling. An auxiliary function generates histograms that are adaptive to patterns in data. This package provides a powerful set of tools for univariate data analysis with guaranteed optimality, efficiency, and reproducibility.

### The main method

The Ckmeans.1d.dp algorithm clusters (weighted) univariate data given by a numeric vector $x$ into $k$ groups by dynamic programming [(Wang and Song, 2011) <doi:10.32614/RJ-2011-015>](https://doi.org/10.32614/RJ-2011-015). It guarantees the optimality of clustering---the total of within-cluster sums of squares is always the minimum given the number of clusters $k$. In contrast, heuristic univariate clustering algorithms may be non-optimal or inconsistent from run to run. As unequal non-negative weights are supported for each point, the algorithm can also segment a time course using the time points as input and the values at each time point as weight. Utilizing the optimal clusters, a function can generate histograms adaptive to patterns in data.

Apart from the time for sorting $x$, the default weighted univariate clustering algorithm takes a runtime of $O(kn)$, linear in both sample size $n$ and the number of clusters $k$, using a new divide-and-conquer strategy integrating a previous theoretical result on matrix search [(Aggarwal et al., 1987) <doi:10.1007/BF01840359>](https://doi.org/10.1007/BF01840359) and a novel in-place search space reduction method. The space complexity is $O(kn)$. This method is numerically stable.

### When to use the package

This package provides a powerful alternative to heuristic clustering and also new functionality for weighted clustering, segmentation, and peak calling with guaranteed optimality.

### To download and install the package
```{r}
install.packages("Ckmeans.1d.dp")
```

pheatmap with larger gaps
========

This project only add one parameter, `gap.size`, for changing the column gaps between clusters. Other functions are exactly same as its parent project, please visit [raivokolde/pheatmap](https://github.com/raivokolde/pheatmap) more information.  

The `gap.size` is equal to `"4"` by default, which is same as its parent. And this gap only shows up when `cutree_rows` or `cutree_cols` is used.

## Installation

```r
devtools::install_github("CoolandHot/bigGapHeatmap")
```

## Usage

```r
out.plot <- bigGapHeatmap::pheatmap(data, gap.size = "6", ...)
```

## Example
<details>
  <summary>source code of this example</summary>
  
  ```r
  # from https://slowkow.com/notes/pheatmap-tutorial/
  random_string <- function(n) {
    substr(paste(sample(letters), collapse = ""), 1, n)
  }

  mat <- matrix(rgamma(1000, shape = 1) * 5, ncol = 50)

  colnames(mat) <- paste(
    rep(1:3, each = ncol(mat) / 3),
    replicate(ncol(mat), random_string(5)),
    sep = ""
  )
  rownames(mat) <- replicate(nrow(mat), random_string(3))

  col_groups <- substr(colnames(mat), 1, 1)

  mat[,col_groups == "1"] <- mat[,col_groups == "1"] * 5

  mat_col <- data.frame(group = col_groups)
  rownames(mat_col) <- colnames(mat)


  bigGapHeatmap::pheatmap(
    mat = mat,
    gap.size = "6",
    cutree_rows = 3,
    cutree_cols = 4,
    fontsize = 14,
    main = "Example Heatmap"
  )

  ```
</details>
![image](/bigGapHeatmap_example.png)

pheatmap with larger gaps
========

This project only add one parameter, `gap.size`, for changing the column gaps between clusters. Other functions are exactly same as its parent project, please visit [it](https://github.com/raivokolde/pheatmap) more information.  

## Installation

```r
devtools::install_github("CoolandHot/bigGapHeatmap")
```

## Usage

```r
out.plot <- bigGapHeatmap::pheatmap(data, gap.size = "6", ...)
```

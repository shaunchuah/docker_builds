# Containerized version of CpGIScan

Original source code here: https://github.com/jzuoyi/cpgiscan 

Paper here: https://www.eurekaselect.com/145427/article

https://doi.org/10.2174/1574893611666160907111325

A CpG island is defined by three types of parameters: the window length, the guanine and cytosine (G + C) frequency, and the ratio of the observed over the expected CpGs (CpG o/e). The algorithm in CpGIScan is based on the sliding window method. To reduce the time required to identify CGIs, multithread technology is employed in our program. CpGIScan was compared to existing widely used tools to benchmark its performance.

### Default settings

Windows length: 500bp
GC frequency: 55%
Observed/expected CpG 0.65

## CpGIScan Options

```
Criteria:
 --length <int> length of lower limit (200-1500,default value:500bp)
 --gcc <int>    %GC of lower limit (50-70,default value:55%)
 --oe <float>   ObsCpG/ExpCpG of lower limit (0.60-1.00,default value:0.65)
Merge:
 --gap <int>    merge two neighboring CpG islands when their distance is
                lower than the gap(e.g. < 100nt)
Output:
 -G <path>      file for GFF output (default: stdout)
 -F <path>      file for fields output
Other:
 -h, --help     print this usage message
```

## Build notes

- Workdir is /data
- Original image is ubuntu 20.04
- Binary file downloaded on 06/09/2021

## Test Docker Command

```
docker run --rm -v ${pwd}:/data cpgiscan -G ./test_output/output.txt ./test_data/hg18-chr21.fa
```

```
docker run --rm -v <mount your directory to /data> -G <output path> <input fasta file>
```

## Docker Repo Location

```
shaunchuah/cpgiscan
```
# CRC atlas - velocyto nextflow pipeline

#TODO: documentation
### 1.1. Usage
```
$ nextflow run main.nf -profile cluster,conda
```

**\<Arguments\>**

--input_csv           = path to the input CSV file (see below for details)

--gtf_file            = path to GTF file (used for the creation of the BAM files)

--masked_repeats      = path to the masked repeats file

--out_dir             = path to the output directory

--publish_dir_mode    = mode of publishDir directive (default: "copy")

--run_10x             = run velocyto run10x command on the samples (default: false - see Note below for details)

**Notes**

**Outpur directory

The pipeline will output the results in the /path/to/Sample.bam directory by default. You need to specify a directory through --out_dir otherwise.

**CSV file (default settings)**
```
study,sample_id,bam,bcl
sample_1,/path/to/Sample1_possorted.bam,/path/to/Sample1_barcodes.tsv
sample_2,/path/to/Sample2_possorted.bam,/path/to/Sample2_barcodes.tsv

```

* If you choose the --run_10x true you need to change the input CSV file to specify the cellranger directories instead of specific bam files (not tested yet)

**CSV file (run_10x flag)**
```
study,sample_id,bam
cohort_1,sample_1,/path/to/Sample1/
cohort_2,sample_2,/path/to/Sample2/

```
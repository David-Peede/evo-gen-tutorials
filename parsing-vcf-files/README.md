# Parsing VCF Files

This directory contains two files (besides this `README.md`):

1. `parsing_vcf_files.ipynb` (the tutorial file) 
2.  `tgp_chr1_first_500_lines.vcf.gz` (the first 500 lines of the chromosome 1 VCF file from the phase 3 release of the 1000 genomes projec)

Here are the steps to re-create `tgp_chr1_first_500_lines.vcf.gz`.

__1. Download the TGP VCF File__

```bash
wget http://ftp.1000genomes.ebi.ac.uk/vol1/ftp/release/20130502/ALL.chr1.phase3_shapeit2_mvncall_integrated_v5b.20130502.genotypes.vcf.gz
```

__2. Extract the First 500 Lines__

```bash
zcat ALL.chr1.phase3_shapeit2_mvncall_integrated_v5b.20130502.genotypes.vcf.gz | head -n 500 > tgp_chr1_first_500_lines.vcf
```

__3. `bgzip` the VCF File with [`tabix`](http://www.htslib.org/doc/tabix.html)__

```bash
bgzip tgp_chr1_first_500_lines.vcf
```


---
author:
  name: "Pei-Wen Shih"
date: 2019-06-09T21:51:13+08:00
emoji: true
linktitle: Insights into Bacterial Genome Sequence Analysis
tags:
- genome assembly
- third generation sequence
title: Insights into Bacterial Genome Sequence Analysis
weight: 10
series: Summer training
image : static
toc : true
---

# Today goals

* Things you should know before assembly
  1. Fastq format
  2. Fasta format
  3. GC- content
  4. Status of genome
* Step to bacterial sequencing analysis


# Things you should know before assembly

## Fastq format
start with `@`

```
@cc3e68c4-b53d-43da-be7e-b961113007e2          -> sequence name
ATCCGGAATCGGTTACTGTTGGGAACCTTTGC               -> sequence
+                                              -> quality line break
#%(*))++.2/148447;7+001./18-7-,,30&*2          -> quality score
```

## Fasta format

start with `>`

```
>tig00000001				           -> sequence name
TGATAAAAGTATTCATATAATCTCCTATCATTTCAAAATTTAAT   -> sequence 
>tig00000002																	 
ATATTAGTGTGTCTATTTTATGGGGCTAGGAAAGGAGGTACATT
```

## GC-content

 the percentage of [nitrogenous bases](https://en.wikipedia.org/wiki/Nitrogenous_bases) on a [DNA](https://en.wikipedia.org/wiki/DNA) or [RNA](https://en.wikipedia.org/wiki/RNA) molecule that are either [guanine](https://en.wikipedia.org/wiki/Guanine) or [cytosine](https://en.wikipedia.org/wiki/Cytosine)
$$
\frac{G+C}{A+T+G+C} \times 100 \%
$$

## Satuts of genome

![genome status](http://ecoevo.unit.oist.jp/lab/wp-content/uploads/2013/08/GenomeAssembly.png)

### 1. contig

   A **contig**  is a set of overlapping DNA segments that together represent a [consensus region of DNA](https://en.wikipedia.org/wiki/Consensus_sequence).

### 2. scaffold

  To bridge the gaps between the two contigs called scaffold.

### 3. complete

  Didn't have fragment, chromesome is in one contig

![complete genome](https://albertsenlab.org/wp-content/uploads/2017/11/longreadsVSshortreads.png)

# Step to bacterial sequencing analysis

![workflow](https://f1000researchdata.s3.amazonaws.com/manuscripts/14771/860b5457-c42e-40df-9829-10ecb2c4b092_figure2.gif)

## Step 1. Quality Control - Assessing the quality of TGS

### 1.1 Checking raw read statistics

Tools : [abyss-fac](https://github.com/bcgsc/abyss)


```
$ abyss-fac -t 1 read.fastq contig.fasta
```

![read-abyssfac](/img/read-abyssfac.png)


* n : Number of raw read

* N50 : A value that present 50% of sorted read set

  ![Alt text](https://i0.wp.com/www.molecularecologist.com/wp-content/uploads/2017/03/Figure1b.jpg?w=699&ssl=1)

* Max: longest read length

* Sum: Total read length

### 1.2 QC report

Tools : [FastQC](https://www.bioinformatics.babraham.ac.uk/projects/fastqc/)


```
$ fastqc -f read.fastq -o outdir
```

## Step 2. Trimming Filtering Data - Preprocessing of raw data (optional)

### 2.1 Filter raw read
Tools : [filtlong](https://github.com/rrwick/Filtlong)

Usually used in **coverage too high**, **trim too short reads**, and want to **keep raw read in between a range**


### 2.2 Demultiplexing, Trimming adapter (barcode)
Tools : [porechop](https://github.com/rrwick/Porechop), [deepbinner](https://github.com/rrwick/Deepbinner)
```
$ porechop -i reads.fastq -o output.fastq # adapter trimming
$ porechop -i reads.fastq -b output.fastq # demultiplexing 
```

## Step 3. Sequence Assembly - Long read genome assembly

### 3.1 De novo assembly
	
    
    
Tools : [Canu](https://canu.readthedocs.io/en/latest/quick-start.html), [Unicycler](https://github.com/rrwick/Unicycler), [Flye](https://github.com/fenderglass/Flye), [Ra](https://github.com/lbcb-sci/ra)

```
$ canu -p genomename -d outdir genomeSize=4.8m -nanopore-raw read.fastq
$ unicycler -l read.fastq -o outdir
		...
```
![de novo](https://pic.pimg.tw/yourgene/1336720283-823145476_n.png)
## Step 4. Assembly Validation

### 4.1 Assembly evaluation

Tools: [abyss-fac](https://github.com/bcgsc/abyss), [assembly-stats](https://github.com/sanger-pathogens/assembly-stats)

1. Total assembly size
2. Total number of sequence
3. Longest contig
4. Average contig size 
5. N50

### 4.2 Assembly status graph

Tools : [Bandage](https://rrwick.github.io/Bandage/)

Is it circular or linear ?

### 4.3 Sequence Similarity Search

Tools : [BLAST](https://blast.ncbi.nlm.nih.gov/Blast.cgi), [MiGA](https://blast.ncbi.nlm.nih.gov/Blast.cgi)

### 4.4 Quality of genomes

Tools : [Checkm](https://ecogenomics.github.io/CheckM/), [busco](https://busco.ezlab.org/)


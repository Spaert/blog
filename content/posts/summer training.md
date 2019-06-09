---
author:
  name: "Pei-Wen Shih"
date: 2019-06-08 09:00:00
emoji: true
linktitle: Insights into Bacterial Genome Sequence Analysis
tags:
- genome assembly
- third generation sequence
title: Insights into Bacterial Genome Sequence Analysis
weight: 10
series: Summer training
toc : true

---

## Today goals

* Introduction - A little about me, lab(~~gossip~~)

* Things you should know before assembly
  1. Fastq format
  2. Fasta format
  3. GC- content
  4. Status of genome
* Step to bacterial sequencing analysis

## Introduction - A little about me, lab(~~gossip~~)

名字： 施佩妏 :smile:

興趣：看美劇、實況、吃雞肉飯

畢業前目標：把嘉義雞肉飯吃一遍

Lab ~~淺~~規則：兩週報一次、問問題

## Things you should know before assembly

#### Fastq format

```
@cc3e68c4-b53d-43da-be7e-b961113007e2          -> sequence name
ATCCGGAATCGGTTACTGTTGGGAACCTTTGC               -> sequence
+                                              -> quality line break
#%(*))++.2/148447;7+001./18-7-,,30&*2          -> quality score
```

#### Fasta format

```
>tig00000001				           -> sequence name
TGATAAAAGTATTCATATAATCTCCTATCATTTCAAAATTTAAT   -> sequence 
>tig00000002																	 
ATATTAGTGTGTCTATTTTATGGGGCTAGGAAAGGAGGTACATT
```

#### GC-content

 the percentage of [nitrogenous bases](https://en.wikipedia.org/wiki/Nitrogenous_bases) on a [DNA](https://en.wikipedia.org/wiki/DNA) or [RNA](https://en.wikipedia.org/wiki/RNA) molecule that are either [guanine](https://en.wikipedia.org/wiki/Guanine) or [cytosine](https://en.wikipedia.org/wiki/Cytosine)
$$
\frac{G+C}{A+T+G+C} \times 100 \%
$$

#### Satuts of genome
![Alt text](http://ecoevo.unit.oist.jp/lab/wp-content/uploads/2013/08/GenomeAssembly.png)

##### 	1. contig

   A **contig**  is a set of overlapping DNA segments that together represent a [consensus region of DNA](https://en.wikipedia.org/wiki/Consensus_sequence).

##### 	2. scaffold

​	To bridge the gaps between the two contigs called scaffold.

##### 	3. complete

  ​	a **circular** genome

![Alt text](https://albertsenlab.org/wp-content/uploads/2017/11/longreadsVSshortreads.png)






---
author:
  name: "Pei-Wen Shih"
date: 2019-06-8
linktitle: Insights into Bacterial Genome Sequence Analysis
type:
- post
- posts
title: Insights into Bacterial Genome Sequence Analysis
weight: 10
series:
- Summer training
---

## Today goals

* Introduction - A little about me, lab(~~gossip~~)

* Things you should know before assembly
  1. [Fastq format](#Fastq-format)
  2. [Fasta format](#Fasta-format)
  3. [GC-content](#GC-content)
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
>tig00000001																	 -> sequence name
TGATAAAAGTATTCATATAATCTCCTATCATTTCAAAATTTAAT   -> sequence 
>tig00000002																	 
ATATTAGTGTGTCTATTTTATGGGGCTAGGAAAGGAGGTACATT
```

#### GC-content

 the percentage of [nitrogenous bases](https://en.wikipedia.org/wiki/Nitrogenous_bases) on a [DNA](https://en.wikipedia.org/wiki/DNA) or [RNA](https://en.wikipedia.org/wiki/RNA) molecule that are either [guanine](https://en.wikipedia.org/wiki/Guanine) or [cytosine](https://en.wikipedia.org/wiki/Cytosine)
$$
\frac{G+C}{A+T+G+C} \times 100 \%
$$





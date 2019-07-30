---
title: Genome alignement and tools
linktitle: Genome alignment and tools 
date: 2019-07-30T18:42:10+08:00
image : static
toc: true
draft: true
---

# Local alignment
![local alignemnt](/img/local alignment.png)

## Blast (Basic Local Alignment Search Tool )

Is an algorithm for comparing primary biological sequence information

| Program  | Query | Search| Database |
|:--:|:--:|:--:|:--:|
| blastn  |  DNA | -> | DNA  |
| blastp  |  protein | -> | protein  |
|  blastx |  DNA |-> | protein  |

* Bit score : 
<font color="#dd0000">*The higher the bit-score, the better the sequence similarity*</font>
* Identity :
$$identity = \frac{match}{total} $$
```
ATCTG
|| ||   identity : 80%
ATATG
```
* E-value :
<font color="#dd0000">*The smaller the E-value, the better the match.*</font>

$$Eval(S)= K *M* N * e^{-lambda*S}$$




# Global alignment


![global alignment](/img/global alignment.png)

## Minimap2
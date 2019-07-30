---
title: "Summer training homework"
linktitle: "Summer training homework"
date: 2019-07-30T20:28:35+08:00
toc: false


---
# 組裝
分別使用[Canu](https://github.com/marbl/canu),[Flye](https://github.com/fenderglass/Flye), [Ra](https://github.com/lbcb-sci/ra), [Shasta](https://chanzuckerberg.github.io/shasta/QuickStart.html)組裝ecoli k-12 標準菌株並製作完整組裝報告

菌株位置：
```
/bip5_disk/peiwen107/medaka_alignment/ecoli/Ecoli_1D.trim.fastq
```

* Step1. Run abyss-fac for raw read
* Step2. Run fastqc 
* Step3. Run Assembler (要計算時間)
* Step4. Analysis result
	1. run blast
	2. run bandage for contig status 
	3. run abyss-fac for contig

* Step5. 製作ppt



# 寫一個python 程式計算gc content
* Step1. 至ncbi 抓取[菌株](https://www.ncbi.nlm.nih.gov/genome/?term=Escherichia+coli)
* Step2. 程式步驟
	1. 讀入fasta檔
	2. 計算sequence的gc content 可使用([SeqIO](https://biopython.org/wiki/SeqIO)做序列處理)
	3. 執行程式必須為此方式
 ```
 > python yourpyscript.py  ecoli.fasta
 output : 
 	gc-content: XX.X%
 ```
 ```
 hint1:
 import sys
 with open(sys.argv[1],'r') as f:
 ```
 ```
 hint2:
 import sys
 from Bio import SeqIO
 record = SeqIO.read(sys.argv[1], "fasta")
 ```





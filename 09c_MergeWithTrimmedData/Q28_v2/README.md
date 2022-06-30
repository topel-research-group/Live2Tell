As with R1-Q28_R2-Q28, but with additional BBmerge filters for low-quality bases

* Using minq=28 doesn't make any difference
* Using ecco for read correction doesn't make any difference

###

Try BBmerge using the newly trimmed Q28 data, with length cutoff?
* No difference to the number of unknowns, only number of merges (as the now-missing merges were from too-short reads anyway)

###

Use this directory to try Mothur for removing chimeras?
```
module load mothur/v1.47.0
mothur

make.file(inputdir=., type=.gz, prefix=C12W1)

# Adjusted C12W1.files manually to make sure the prefixes in column 1 were correct, and removed the C2W24 samples I'd inadvertently included

make.contigs(file=C12W1.files, processors=20)

# Check summary of results
summary.seqs(fasta=C12W1.trim.contigs.fasta, count=C12W1.contigs.count_table, processors=20)

# Get unique sequences and counts
unique.seqs(fasta=C12W1.trim.contigs.fasta, count=C12W1.contigs.count_table)

# Update summary
summary.seqs(fasta=C12W1.trim.contigs.unique.fasta, count=C12W1.trim.contigs.count_table, processors=20)

# Will it work to try and remove chimeras without first aligning to the reference?
chimera.vsearch(fasta=C12W1.trim.contigs.unique.fasta, reference=../C12W1_all.withR05.v2.fasta, dereplicate=t, processors=32)


```

Running on individual samples - _135 identified 39 chimeras (0.1%) (plus five borderline seqs) in 63,705 seqs
* More merges than reported using BBmerge
* Note that the total sequences includes the other three barcodes

Running on a mixed sample - _275 identified 2,786 chimeras (1.4%) (plus 119 borderline seqs) in 202,655 seqs
* Many more merges than reported using BBmerge

###

Number of successful mergers per barcode

|   Sample   | C2W24  | C12W1  | C12W2  | C16W4  | Other |
|------------|--------|--------|--------|--------|-------|
| P21502_101 |     23 |     15 |      5 |      6 |     0 |
| P21502_102 |  1,330 |    739 |    232 |    401 |     0 |
| P21502_103 |  6,912 |  3,243 |  1,076 |  2,203 |     0 |
| P21502_104 |     91 |     51 |     21 |     32 |     0 |
| P21502_105 |    684 |    507 |    222 |    336 |     0 |
| P21502_107 |    144 |     87 |     48 |     46 |     0 |
| P21502_108 |  5,281 |  2,606 |  1,443 |  3,045 |     0 |
| P21502_109 |  8,211 |  4,149 |    482 |  1,245 |     0 |
| P21502_110 | 12,678 |  7,062 |  2,250 |  6,033 |     0 |
| P21502_111 |  4,700 |  2,880 |  1,496 |  1,819 |     0 |
| P21502_112 |  3,255 |  1,973 |  2,252 |  1,425 |     0 |
| P21502_113 |  3,195 |    466 |  1,374 |     70 |     0 |
| P21502_114 |    176 |  1,808 |  1,988 |  3,535 |     0 |
| P21502_115 |  3,697 |  3,837 |  2,343 |  5,791 |     0 |
| P21502_116 |  6,489 |  1,205 |    418 |  1,652 |     0 |
| P21502_117 |  4,476 |  2,595 |    731 |    936 |     0 |
| P21502_118 |  6,942 |  3,824 |    608 |  1,784 |     1 | *******
| P21502_119 |      5 |     21 |     10 |     10 |     0 |
| P21502_120 |  9,706 |  2,318 |  2,400 |  4,732 |     1 | *******
| P21502_121 |  6,193 |  2,940 |    837 |  2,545 |     0 |
| P21502_122 |    383 |  3,681 |  2,306 |  3,871 |     1 | *******
| P21502_123 |  4,220 |  4,904 |  2,276 |  4,934 |     0 |
| P21502_124 |  4,913 |  2,953 |    421 |  1,417 |     0 |
| P21502_125 |  5,944 |  9,448 |    263 |  1,228 |     0 |
| P21502_126 |     26 |  4,146 |  1,335 |  2,781 |     0 |
| P21502_127 | 10,325 |  4,637 |  2,393 |  5,087 |     0 |
| P21502_128 |  2,043 |  3,073 |  1,703 |  3,761 |     0 |
| P21502_129 |  1,783 |  2,601 |  1,260 |  3,293 |     0 |
| P21502_130 |    119 |  2,602 |  1,487 |  3,058 |     0 |
| P21502_131 |    338 |  3,251 |  1,840 |  4,411 |     0 |
| P21502_132 |  5,420 |  2,651 |    849 |  2,220 |     0 |
| P21502_133 |  9,262 |  6,924 |    662 |  2,348 |     1 | *******
| P21502_134 |  8,010 |  5,365 |    205 |    506 |     0 |
| P21502_135 | 18,371 | 10,934 |  2,317 |  3,193 |     1 | *******
| P21502_136 |  4,215 |  2,284 |  1,358 |  3,155 |     0 |
| P21502_137 |  5,831 |  4,033 |  1,701 |    750 |     0 |
| P21502_138 |     15 |  5,097 |  2,255 |  3,257 |     0 |
| P21502_139 |  6,439 |  2,389 |  2,231 |  4,576 |     0 |
| P21502_140 |  2,100 |  1,348 |    880 |  1,267 |     0 |
| P21502_141 |  1,452 |  3,717 |  2,589 |  3,714 |     0 |
| P21502_142 |     11 |  1,984 |    704 |  2,362 |     0 |
| P21502_143 | 35,434 |  9,727 |  2,824 |  6,826 |     0 |
| P21502_144 |  9,056 |  9,182 |  4,053 |  7,300 |     0 |
| P21502_145 |  6,841 |  2,205 |    900 |  2,403 |     0 |
| P21502_146 |     88 |  8,788 |  6,960 | 19,143 |     0 |
| P21502_147 |    172 |  4,607 |  4,092 |  9,819 |     0 |
| P21502_148 |  9,166 |  2,954 |  1,154 |  3,409 |     0 |
| P21502_149 |     19 |  7,432 |  1,030 |  4,313 |     0 |
| P21502_150 |  5,872 |  3,725 |    385 |  1,307 |     1 | *******
| P21502_151 | 10,195 |  5,981 |  2,818 |  6,183 |     0 |
| P21502_152 |     11 |  2,428 |    373 |    910 |     0 |
| P21502_153 |  7,635 |  3,761 |  1,101 |  1,878 |     0 |
| P21502_154 |    531 |  7,816 |  4,048 |  8,126 |     0 |
| P21502_155 |  1,420 |  3,256 |  1,772 |  4,315 |     0 |
| P21502_156 |  4,586 |  2,856 |    697 |  2,034 |     1 | *******
| P21502_157 |  1,297 |  5,421 |  4,220 |  5,599 |     0 |
| P21502_158 |     10 |  3,366 |  1,140 |  1,558 |     0 |
| P21502_159 | 17,478 |  6,796 | 14,180 |  3,023 |     1 | *******
| P21502_160 |     50 |  3,856 |  4,007 |  4,538 |     0 |
| P21502_161 |     68 |  3,970 |  1,027 |     69 |     0 |
| P21502_162 |      0 |  3,828 |    748 |    730 |     0 |
| P21502_163 |    198 | 20,619 | 14,519 | 26,638 |     0 |
| P21502_164 |      8 |  5,284 |  1,227 |  1,271 |     0 |
| P21502_165 |     80 |      4 |  5,820 |      0 |     3 | *******
| P21502_166 |      2 |      1 |  5,157 |      0 |     0 |

# Do the barcodes match our expectations?

* C2W24 - two sequences expected - CATGAAACGGAAACTCTGAGCAC.*CATTGAACTCGAAACGCAGCATATT
* C12W1 - four sequences expected - AGG.TTCGCCTCCTCAAAC.*CTTTGCGTGTGCATCGTGCC
* C12W2 - two sequences expected - CCCTCCAATACGCAACAATCC.*GGTGGGACGTGTGGAATTG
* C16W4 - four sequences expected - CTGGTCC.ATCAAGTGTGTGTCATC.*C.TCCACTCTCCTCACGGGAA

Note - Y is a C/T ambiguous base, so in the barcodes derived from the merged reads, I've subbed C/T for Y in the relevant positions for ease of comparison
Note - W is an A/T ambiguous base, so in the barcodes derived from the merged reads, I've subbed A/T for W in the relevant positions for ease of comparison

Can run comparisons using the following one-liners:
```
cat *barcodes.fasta | fasta2tab | grep "C2W24" | tab2fasta
cat *barcodes.fasta | fasta2tab | grep "C12W1" | tab2fasta
cat *barcodes.fasta | fasta2tab | grep "C12W2" | tab2fasta
cat *barcodes.fasta | fasta2tab | grep "C16W4" | tab2fasta
```

# Identical sequences

## C12W1
* P21502_102_C12W1_3? + P21502_117_C12W1_2 !
* P21502_105_C12W1_2 + P21502_113_C12W1_2 !
* P21502_116_C12W1_1 + P21502_145_C12W1_2
* P21502_103_C12W1_2 + P21502_136_C12W1_2
* P21502_105_C12W1_1 + P21502_113_C12W1_1 !
* P21502_127_C12W1_1 + P21502_142_C12W1_2
* P21502_108_C12W1_1 + P21502_147_C12W1_1
* P21502_121_C12W1_2 + P21502_110_C12W1_2 + P21502_152_C12W1_1
* P21502_104_C12W1_1 + P21502_112_C12W1_1
* P21502_102_C12W1_4? + P21502_117_C12W1_1 !
* P21502_114_C12W1_1 + P21502_115_C12W1_2 !
* P21502_101_C12W1_1 + P21502_107_C12W1_1
* P21502_114_C12W1_2 + P21502_115_C12W1_1 !

		P14203_105 and P14203_111 seem to be identical?
		* P14203_111 was low coverage so reasonable that this could have been missed
		Check P14203_102 and P14203_115
		* Could P14203_102 have become contaminated with P14203_115?
		P14203_112 and P14203_113 seem to be identical?
		* These were noted as identical previously so this makes sense

## C12W2
* P21502_114_C12W2_1 + P21502_115_C12W2_1 !
* P21502_116_C12W2_2 + P21502_145_C12W2_2
* P21502_114_C12W2_2 + P21502_115_C12W2_2 !
* P21502_109_C12W2_1 + P21502_109_C12W2_1
* P21502_104_C12W2_3? + P21502_112_C12W2_1 !
* P21502_131_C12W2_2 + P21502_142_C12W2_2
* P21502_110_C12W2_1 + P21502_151_C12W2_1
* P21502_104_C12W2_4? + P21502_112_C12W2_2 !
* P21502_102_C12W2_1 + P21502_119_C12W2_2 + P21502_125_C12W2_1 + P21502_153_C12W2_2
* P21502_105_C12W2_3? + P21502_113_C12W2_2
* P21502_133_C12W2_2 + P21502_149_C12W2_2
* P21502_111_C12W2_2 + P21502_129_C12W2_1 + P21502_152_C12W2_2
* P21502_102_C12W2_5? + P21502_117_C12W2_2 !
* P21502_102_C12W2_3? + P21502_117_C12W2_1 !
* P21502_130_C12W2_1 + P21502_154_C12W2_2
* P21502_101_C12W2_2? + P21502_107_C12W2_2
* P21502_102_C12W2_4? + P21502_103_C12W2_1
* P21502_105_C12W2_4? + P21502_113_C12W2_1 + P21502_139_C12W2_1 !

		P14203_112 and P14203_113 seem to be identical?
		* These were noted as identical previously so this makes sense
		Check P14203_104 and P14203_110
		* Could P14203_104 have become contaminated with P14203_110?
		Check P14203_102 and P14203_115
		* Could P14203_102 have become contaminated with P14203_115?
		P14203_105 and P14203_111 seem to be identical?
		* P14203_111 was low coverage so reasonable that this could have been missed

## C16W4
* P21502_147_C16W4_1 + P21502_150_C16W4_1
* P21502_105_C16W4_4? + P21502_113_C16W4_2 + P21502_122_C16W4_2 !
* P21502_114_C16W4_1 + P21502_115_C16W4_1 !
* P21502_101_C16W4_1 + P21502_118_C16W4_2
* P21502_105_C16W4_3? + P21502_113_C16W4_1 !
* P21502_122_C16W4_1 + P21502_123_C16W4_1
* P21502_114_C16W4_2 + P21502_115_C16W4_2 !
* P21502_119_C16W4_2 + P21502_135_C16W4_2
* P21502_102_C16W4_3? + P21502_117_C16W4_1
* P21502_104_C16W4_3? + P21502_112_C16W4_1
* P21502_107_C16W4_2 + P21502_141_C16W4_1

		Check P14203_105 and P14203_111 (identical?)
		* P14203_111 was low coverage so reasonable that this could have been missed
		* However, P14203_105 also contains additional sequences here...
		P14203_112 and P14203_113 seem to be identical?
		* These were noted as identical previously so this makes sense



In samples with a decent number of reads, there is usually a big jump in the number of identical sequences, which likely marks where the
'good' results end and the bad results begin (although there are primer dimers in the high frequency sequences)
* Check these high frequency results

|   Sample   |             C2W24              |             C12W1              |             C12W2              |             C16W4              |   Notes   |
|------------|--------------------------------|--------------------------------|--------------------------------|--------------------------------|-----------|
| P14203_101 |         Doesn't match          | Both alleles match predictions |   Both found but low support   |   Both found but low support   | Few reads |
| P14203_102 |         Doesn't match          |  Both alleles and more found!  |  Both alleles and more found!  |  Both alleles and more found!  | Few reads |
| P14203_103 | Doesn't match, esp. in repeats | Both alleles match predictions | Both alleles match predictions | Both alleles match predictions |     -     |
| P14203_104 |         Doesn't match          | One allele, doesn't match pred.|  Both alleles and more found!  |  Both alleles and more found!  | Few reads |
| P14203_105 |         Doesn't match          |  Both alleles and more found!  |  Both alleles and more found!  |  Both alleles and more found!  | Few reads |
| P14203_106 |               NA               |               NA               |               NA               |               NA               |    NA     |
| P14203_107 | Doesn't match, esp. in repeats | Both alleles match predictions | Both alleles match predictions | One position differs from pred.|     -     |
| P14203_108 | Doesn't match, esp. in repeats | Both alleles match predictions | Both alleles match predictions | Both alleles match predictions |     -     |
| P14203_109 |         Doesn't match          | Both alleles match predictions | Both alleles match predictions | Both alleles match predictions |     -     |
| P14203_110 | Doesn't match, esp. in repeats |      One allele missing...     | Both alleles match predictions | Both alleles match predictions |     -     |
| P14203_111 | Doesn't match, esp. in repeats | Ref. a mix of the new alleles  |             Weird              |             Weird              |     -     |
| P14203_112 |         Doesn't match          | Both alleles match predictions | Both alleles match predictions | Both alleles match predictions |     -     |
| P14203_113 |         Doesn't match          | One position differs from pred.| Both alleles match predictions | Both alleles match predictions |     -     |
| P14203_114 |         Doesn't match          | One position differs from pred.| Both alleles match predictions | Both alleles match predictions |     -     |
| P14203_115 |         Doesn't match          | Both alleles match predictions | Both alleles match predictions |  A few differences from pred.  |     -     |
| P14203_116 |         Doesn't match          | Both alleles match predictions | Both alleles match predictions | Both alleles match predictions |     -     |
| P14203_117 |         Doesn't match          |  A few differences from pred.  | Alleles found but also noise?  |  A few differences from pred.  | Few reads |
| P14203_118 |         Doesn't match          | Both alleles match predictions | Both alleles match predictions | Both alleles match predictions |     -     |
| P14203_119 |         Doesn't match          | Both alleles match predictions | Both alleles match predictions |  A few differences from pred.  |     -     |
| P14203_120 |         Doesn't match          | Both alleles match predictions | Both alleles match predictions | Both alleles match predictions |     -     |
| P14203_121 |         Doesn't match          | Both alleles match predictions | Both alleles match predictions |  A few differences from pred.  |     -     |
| P14203_122 |         Doesn't match          | Both alleles match predictions | Both alleles match predictions | Both alleles match predictions |     -     |
| P14203_123 |         Doesn't match          |   Neither allele matches...    |  A few differences from pred.  | Both alleles match predictions |     -     |
| P14203_124 |         Doesn't match          | Both alleles match predictions | Both alleles match predictions | Both alleles match predictions |     -     |
| P14203_125 |         Doesn't match          | Both alleles match predictions | Both alleles match predictions | Both alleles match predictions |     -     |
| P14203_126 |         Doesn't match          | Both alleles match predictions | Both alleles match predictions | Both alleles match predictions |     -     |
| P14203_127 |         Doesn't match          | Both alleles match predictions | Both alleles match predictions | Both alleles match predictions |     -     |
| P14203_128 |         Doesn't match          | Both alleles match predictions | Both alleles match predictions | Both alleles match predictions |     -     |
|------------|--------------------------------|--------------------------------|--------------------------------|--------------------------------|-----------|
| P14203_129 |      One allele matches!       | Both alleles match predictions | Both alleles match predictions | Both alleles match predictions |     -     |
| P14203_130 |         Doesn't match          | Both alleles match predictions | Both alleles match predictions | Both alleles match predictions |     -     |
| P14203_131 |         Doesn't match          | Both alleles match predictions | Both alleles match predictions | Both alleles match predictions |     -     |
| P14203_132 |         Doesn't match          | Both alleles match predictions | One position differs from pred.| Both alleles match predictions |     -     |
| P14203_133 |         Doesn't match          | Both alleles match predictions | Both alleles match predictions | Both alleles match predictions |     -     |
| P14203_134 |         Doesn't match          |  A few differences from pred.  |  A few differences from pred.  | One position differs from pred.|     -     |
| P14203_135 |         Doesn't match          | Both alleles match predictions |  A few differences from pred.  | Both alleles match predictions |     -     |
| P14203_136 |         Doesn't match          | Both alleles match predictions | Both alleles match predictions | Both alleles match predictions |     -     |
| P14203_137 |         Doesn't match          | Both alleles match predictions |  A few differences from pred.  |  A few differences from pred.  |     -     |
| P14203_138 |         Doesn't match          | Both alleles match predictions |  A few differences from pred.  | Both alleles match predictions |     -     |
| P14203_139 |         Doesn't match          | Both alleles match predictions | Both alleles match predictions | One position differs from pred.|     -     |
| P14203_140 |         Doesn't match          | Both alleles match predictions | Both alleles match predictions | Both alleles match predictions |     -     |
| P14203_141 |         Doesn't match          | Three barcodes, none match...  | Three barcodes, none match...  | Three barcodes, none match...  |     -     |
| P14203_142 |         Doesn't match          | Both alleles match predictions | Both alleles match predictions | Both alleles match predictions |     -     |
| P14203_143 |         Doesn't match          | Both alleles match predictions | Both alleles match predictions | Both alleles match predictions |     -     |
| P14203_144 |         Doesn't match          | Both alleles match predictions | Both alleles match predictions | Both alleles match predictions |     -     |
| P14203_145 |         Doesn't match          | Both alleles match predictions | Both alleles match predictions | Both alleles match predictions |     -     |
| P14203_146 |         Doesn't match          | One position differs from pred.| Both alleles match predictions | Both alleles match predictions |     -     |
| P14203_147 |         Doesn't match          | Both alleles match predictions | Both alleles match predictions | Both alleles match predictions |     -     |
| P14203_148 |         Doesn't match          | Both alleles match predictions | Both alleles match predictions | Both alleles match predictions |     -     |
| P14203_149 |         Doesn't match          | Both alleles match predictions | Both alleles match predictions | Both alleles match predictions |     -     |
| P14203_150 |         Doesn't match          | Both alleles match predictions |  A few differences from pred.  | Both alleles match predictions |     -     |
| P14203_151 |         Doesn't match          | Both alleles match predictions | Both alleles match predictions | Both alleles match predictions |     -     |
| P14203_152 |         Doesn't match          | Both alleles match predictions | One position differs from pred.| Both alleles match predictions |     -     |
| P14203_153 |         Doesn't match          | Both alleles match predictions | Both alleles match predictions | Both alleles match predictions |     -     |
| P14203_154 |         Doesn't match          | Both alleles match predictions | One position differs from pred.| Both alleles match predictions |     -     |
| P14203_155 |      One allele matches!       | Both alleles match predictions | Both alleles match predictions | Both alleles match predictions |     -     |
| P14203_156 |         Doesn't match          |  A few differences from pred.  | Both alleles match predictions | Both alleles match predictions |     -     |

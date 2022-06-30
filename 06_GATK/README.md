# See whether GATK provides more reliable variant calling than bcftools

|        Run       |  Results   |
|------------------|------------|
|     p21 w500     |  1 window  | (same with new iteration of pipeline)
|     p21 w300     | No windows |
| p21 w500, no 112 |  4 windows |
| p21 w300, no 112 | No windows |

Results used for the final paper were generated using commit 75467da

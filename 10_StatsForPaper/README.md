1. Identify the length of the regions under consideration in the Bamboozle pipeline

  * Run each sample's BAM file through an altered part of the Bamboozle pipeline,
    identifying regions of the genome with weird coverage
  * Merge results from all BAMs to find all positions with weird coverage across all samples
  * With 500bp windows, step through the genome and find all windows which don't overlap
    regions of unusual coverage by 10+ bp (this allows for short indels, including 3aa frameshifts)

  Output is a BED file containing all of the 500bp windows which have acceptable coverage

Windows can just be extracted from good_cov_list pickle from the ongoing job!


2. Identify the average number of SNP sites in the identified windows

  * For the above regions, calculate the number of sites containing SNPs

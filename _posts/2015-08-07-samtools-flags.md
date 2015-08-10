---
layout: post
title: SAMtools flags
date: 2015-08-03 17:00:00
summary: SAMtools flags for every occasion.
tags: ["samtools","genomics","bioinformatics"]
---

This afternoon, in the office, we were trying get our heads round what seemed
like a fairly trivial task. Well, it probably is fairly trivial, but I figured
I would write it all down somewhere for future reference.

From a mapping of paired-end Illumina HiSeq reads to some MEGAHIT contigs, we
were trying to get lists of IDs of reads that were:

1. Mapped pairs.
2. Unmapped pairs.
3. Unmapped forward reads.
4. Unmapped reverse reads.

Now, [this page](https://broadinstitute.github.io/picard/explain-flags.html)
in the Picard documentation has a really handy overview of
all of the flags, but doesn't show combinations of `-f` and `-F` (output/don't output) flags. Anyway, without further ado, here is a series of commands to output lists of read IDs for the above tasks (and a couple of extra).

**Mapped pairs (fwd. and rev. both mapped)**  
`samtools view -f 2 mapping.sorted.bam | cut -f1 | sort | uniq`

**Unmapped (fwd. or rev. or both unmapped)**  
`samtools view -F 2 mapping.sorted.bam | cut -f1 | sort | uniq`

**Mapped fwd.**  
`samtools view -F 4 -f 64 mapping.sorted.bam | cut -f1 | sort | uniq`

**Mapped rev.**  
`samtools view -F 4 -f 128 mapping.sorted.bam | cut -f1 | sort | uniq`

**Unmapped fwd.**  
`samtools view -f 68 mapping.sorted.bam | cut -f1 | sort | uniq`

**Unmapped rev.**  
`samtools view -f 72 mapping.sorted.bam | cut -f1 | sort | uniq`

**Mapped fwd. (rev. is unmapped), or vice versa**  
`samtools view -f 64 -F 6 mapping.sorted.bam | cut -f1 | sort | uniq`

**Mapped rev. (fwd. is unmapped), or vice versa**  
`samtools view -f 128 -F 6 mapping.sorted.bam | cut -f1 | sort | uniq`

And if you just want counts of the above, then add `| wc -l` to the end of any of the above commands.

Hopefully someone will find that useful...?

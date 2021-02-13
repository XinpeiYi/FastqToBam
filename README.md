# FastqToBam

#### Build hg38 index
bowtie2-build Homo_sapiens_assembly38.fasta hg38

#### Transfer fastq to sam file
bowtie2  -x hg38 -1 111_R1.fq.gz -2 111_R2.fq.gz  -S 111.sam --thread 20

#### Transfer sam to bam file
samtools view -bS 111.sam -o 111.bam

#### Sort bam
samtools sort 111.bam -o 111.sorted.bam --threads 20

#### Index bam
samtools index 111.sorted.bam


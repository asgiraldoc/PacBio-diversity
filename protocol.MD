### assembly consensus seq

canu -d test -p test genomeSize=6k -pacbio <fasta file>

### mapping

minimap2 -a test.contigs.fasta ../AE98_For_bc1020--Rev_bc1098.fasta > alingment.sam

samtools faidx test.contigs.fasta 

samtools view -bS alingment.sam > alingment.bam

samtools sort alingment.bam -o alingment_sort.bam

samtools index alingment_sort.bam

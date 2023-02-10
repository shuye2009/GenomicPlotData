source of data:

-- from /home/greenblattlab/shuyepu/Nujhat/ChIPseq/ZNF768_684_281/GREENBLATT
-rw-r--r-- 1 shuyepu greenblattlab 1.7G Sep 23 09:27 ZNF281_ChIP_2_S12_sorted_dedup.bam
-rw-r--r-- 1 shuyepu greenblattlab 2.3M Sep 23 09:39 ZNF281_ChIP_2_S12_sorted_dedup.bam.bai
-rw-r--r-- 1 shuyepu greenblattlab 2.6G Sep 23 09:29 ZNF281_Input_1_S9_sorted_dedup.bam
-rw-r--r-- 1 shuyepu greenblattlab 2.3M Sep 23 09:39 ZNF281_Input_1_S9_sorted_dedup.bam.bai

-- from /home/greenblattlab/shuyepu/Nujhat/ChIPseq/ZNF768_684_281/GREENBLATT/macs2_results
-rw-r--r-- 1 shuyepu greenblattlab 8.4M Sep 23 09:34 ZNF281_ChIPseq_peaks.narrowPeak
-rw-r--r-- 1 shuyepu greenblattlab 5.8M Sep 23 09:34 ZNF281_ChIPseq_summits.bed

-- from /home/greenblattlab/shuyepu/Nabeel/clip_analysis/data_input/CLIP_cits/SP1_CITS_crosslinkSite
-rw-r--r-- 1 shuyepu greenblattlab  61M Sep 22 09:37 combined_CITS_0.01_SP1.merged_filtered.bed

-- from /home/greenblattlab/shuyepu/Nabeel/clip_analysis/data_input/Input_bam
-rwxr-x--- 1 shuyepu greenblattlab 194M Sep 22 09:39 Input_SP1.A.thUni.bam
-rwxr-x--- 1 shuyepu greenblattlab 4.5M Sep 22 09:39 Input_SP1.A.thUni.bam.bai

-- from /home/greenblattlab/shuyepu/Nabeel/clip_analysis/data_input/SP1_2021/CLIP_bam
-rw-r--r-- 1 shuyepu greenblattlab 2.3G Sep 22 09:46 SP1_S2S3E.merged.bam
-rw-r--r-- 1 shuyepu greenblattlab 3.9M Sep 22 09:46 SP1_S2S3E.merged.bam.bai

-- from following commands
-rw-r--r-- 1 shuyepu greenblattlab 3.9M Sep 22 09:50 test_clip_peak_chr19.bed
-rw-r--r-- 1 shuyepu greenblattlab 116K Sep 22 09:52 test_chip_peak_chr19.bed
-rw-r--r-- 1 shuyepu greenblattlab 8.2M Sep 22 10:10 test_clip_input_chr19.bam
-rw-r--r-- 1 shuyepu greenblattlab  61M Sep 22 10:11 test_chip_chr19.bam
-rw-r--r-- 1 shuyepu greenblattlab  60M Sep 22 10:12 test_chip_input_chr19.bam
-rw-r--r-- 1 shuyepu greenblattlab 113M Sep 22 10:13 test_clip_chr19.bam
-rw-r--r-- 1 shuyepu greenblattlab 171K Sep 22 10:14 test_chip_peak_chr19.narrowPeak
-rw-r--r-- 1 shuyepu greenblattlab  44K Sep 22 10:16 test_chip_chr19.bam.bai
-rw-r--r-- 1 shuyepu greenblattlab  45K Sep 22 10:16 test_chip_input_chr19.bam.bai
-rw-r--r-- 1 shuyepu greenblattlab  76K Sep 22 10:16 test_clip_chr19.bam.bai
-rw-r--r-- 1 shuyepu greenblattlab  83K Sep 22 10:16 test_clip_input_chr19.bam.bai

commands:

grep "chr19" combined_CITS_0.01_SP1.merged_filtered.bed > test_clip_peak_chr19.bed
grep "chr19" ZNF281_chipseq_summits.bed > test_chip_peak_chr19.bed
grep "chr19" ZNF281_chipseq_peaks.narrowPeak > test_chip_peak_chr19.narrowPeak
/usr/bin/samtools view Input_SP1.A.thUni.bam chr19 -b > test_clip_input_chr19.bam
/usr/bin/samtools view ZNF281_ChIP_2_S12_sorted_dedup.bam chr19 -b > test_chip_chr19.bam
/usr/bin/samtools view ZNF281_Input_1_S9_sorted_dedup.bam chr19 -b > test_chip_input_chr19.bam
/usr/bin/samtools view SP1_S2S3E.merged.bam chr19 -b > test_clip_chr19.bam
for f in *_chr19.bam; do /usr/bin/samtools index $f; done

mv combined_CITS_0.01_SP1.merged_filtered.bed test_clip_peak.bed
mv Input_SP1.A.thUni.bam test_clip_input.bam
mv Input_SP1.A.thUni.bam.bai test_clip_input.bam.bai
mv ZNF281_ChIP_2_S12_sorted_dedup.bam test_chip.bam
mv ZNF281_ChIP_2_S12_sorted_dedup.bam.bai test_chip.bam.bai
mv ZNF281_ChIPseq_peaks.narrowPeak test_chip_peak.narrowPeak
mv ZNF281_ChIPseq_summits.bed test_chip_peak.bed
mv ZNF281_Input_1_S9_sorted_dedup.bam test_chip_input.bam
mv ZNF281_Input_1_S9_sorted_dedup.bam.bai test_chip_input.bam.bai
mv SP1_S2S3E.merged.bam test_clip.bam
mv SP1_S2S3E.merged.bam.bai test_clip.bam.bai


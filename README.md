# STR-realigner

## OVERVIEW

STR-realigner is a Java program that extracts and realigns sequence reads in input SAM/BAM file around prespecified short tandem repeat regions. Realigned sequence reads are saved as SAM/BAM format and used for variant calling with existing STR call software tools.

## INPUT

The sequence read data in SAM or BAM format
A list of STR regions

## OUTPUT

Variant calling and haplotype phasing results in VCF format

## USAGE

Example

~~~~
java -jar STR-realigner.jar \  
    Realign \
    <SAM or BAM file> \
    <Fasta file>
    <STR region file>
  
~~~~



## OPTIONS

| Option | Default Value | Summary |
|--------|:--------------|:--------|
| -r (--reference) | STR none | Reference genome fasta file| 
| --fusion-distance | INT none | window distance for unifying realignment target regions |
| --gap-extension-penalty-realign | DOUBLE none | gap exntesion penalty for STR region |
|* -c (--call-range-size) | INT 2500000 | Variant calling range size |
| -h (--help) | false | Print options and exit |
| -i (--iteration) | INT 20 | Iteration count |
| -il (--illumina) | [true/false] false | Use Illumina HiSeq read correction mode |
| -l (--depth-limit) | INT 500 | Depth limit |
| -m (--margin) | INT 1000 | Margin for variant calling |
| -p (--use-paired-end) | [true/false] true | Consider paired-end reads |
| -rp (--reference-prior) | DOUBLE 0.135 | Prior strength for reference allele |
| -th (--threshold) | DOUBLE 10.0 | Threshold for filtering variant calls |
| -u (--unit-id) | INT 1 | Unit ID |

## DOWNLOAD

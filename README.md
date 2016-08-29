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

| Option | Value Type | Default | Summary |
|--------|:-----------|:--------|:--------|
| --fusion-distance | INT | none | window distance for unifying realignment target regions |
| -h (--help) | BOOLEAN / false | Print options and exit |
| --margin | INT 100 | margin for realignment region |
| --skip-homopolymer-size | INT / 15 | homopolymer size skipped in realignment |
| --fusion-distance | INT / 80  | window distance for unifying realignment target regions |
| --match-penalty-realign | DOUBLE | -1.0 | match penalty in target microsatellite region |
| --mismatch-penalty | DOUBLE | -1.0 | mismatch penalty in target microsatellite region |
| --gap-open-penalty | DOUBLE | 2.0 | gap open penalty in target microsatellite region |
| --gap-open-extension-realign | DOUBLE | 2.0 | gap extension penalty in target microsatellite region |
| --match-penalty-realign | DOUBLE | -1.0 | match penalty in target microsatellite region |
| --mismatch-penalty-realign | DOUBLE | -1.0 | mismatch penalty in target microsatellite region |
| --gap-open-penalty-realign | DOUBLE | 2.0 | gap open penalty in target microsatellite region |
| --gap-open-extension-realign | DOUBLE | 2.0 | gap extension penalty in target microsatellite region |

## DOWNLOAD

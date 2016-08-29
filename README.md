# STR-realigner

## OVERVIEW

STR-realigner is a Java program that extracts and realigns sequence reads in input SAM/BAM file around prespecified short tandem repeat regions. Realigned sequence reads are saved as SAM/BAM format and used for variant calling with existing STR call software tools.

## INPUT

The sequence read data in SAM or BAM format
A list of STR regions

## OUTPUT

Variant calling and haplotype phasing results in VCF format

## BASIC USAGE

Obtain a file for STR regions for realignment with the following command:

~~~~
java -jar STR-realigner.jar \  
    RegionFinder \
    --output <STR region file for realignment>
    <Fasta file> \
    <STR region file>
  
~~~~

<STR region file> is given as the following format:

~~~~
chr22:17070462-17070484 T
chr22:17070981-17070996 CT
chr22:17071583-17071602 A
chr22:17074193-17074211 T
chr22:17075735-17075759 T
chr22:17075881-17075895 AAAG
chr22:17076890-17076933 AAAT
chr22:17077218-17077235 AAAAT
...
~~~~

By applying the obtained <STR region file for alignment>, reads in <Input SAM or BAM file> is realigned:

~~~~
java -jar STR-realigner.jar \  
    Realign \
    --output-file <Realigned BAM file> \
    <Input SAM or BAM file> \
    <Fasta file> \
    <STR region file>
  
~~~~



## OPTIONS

For Realign
| Option | Value Type | Default | Summary |
|--------|:-----------|:--------|:--------|
| --fusion-distance | INT | none | window distance for unifying realignment target regions |
| -h (--help) | BOOLEAN | false | Print options and exit |
| --margin | INT 100 | margin for realignment region |
| --output-file | STR | none | output BAM file with realigned reads (SAM format text is printed to stdout without option |
| --skip-homopolymer-size | INT | 15 | homopolymer size skipped in realignment |
| --fusion-distance | INT | 80  | window distance for unifying realignment target regions |
| --match-penalty-realign | DOUBLE | -1.0 | match penalty in target microsatellite region |
| --mismatch-penalty | DOUBLE | -1.0 | mismatch penalty in target microsatellite region |
| --gap-open-penalty | DOUBLE | 2.0 | gap open penalty in target microsatellite region |
| --gap-open-extension-realign | DOUBLE | 2.0 | gap extension penalty in target microsatellite region |
| --match-penalty-realign | DOUBLE | -1.0 | match penalty in target microsatellite region |
| --mismatch-penalty-realign | DOUBLE | -1.0 | mismatch penalty in target microsatellite region |
| --gap-open-penalty-realign | DOUBLE | 2.0 | gap open penalty in target microsatellite region |
| --gap-open-extension-realign | DOUBLE | 2.0 | gap extension penalty in target microsatellite region |

For RegionFinder
| Option | Value Type | Default | Summary |
|--------|:-----------|:--------|:--------|
| --fusion-distance | INT | none | window distance for unifying realignment target regions |
| -h (--help) | BOOLEAN | false | Print options and exit |
| --margin | INT 100 | margin for realignment region |
| --output-file | STR | none | output BAM file with realigned reads (SAM format text is printed to stdout without option |
| --skip-homopolymer-size | INT | 15 | homopolymer size skipped in realignment |
| --fusion-distance | INT | 80  | window distance for unifying realignment target regions |
| --match-penalty-realign | DOUBLE | -1.0 | match penalty in target microsatellite region |
| --mismatch-penalty | DOUBLE | -1.0 | mismatch penalty in target microsatellite region |
| --gap-open-penalty | DOUBLE | 2.0 | gap open penalty in target microsatellite region |
| --gap-open-extension-realign | DOUBLE | 2.0 | gap extension penalty in target microsatellite region |
| --match-penalty-realign | DOUBLE | -1.0 | match penalty in target microsatellite region |
| --mismatch-penalty-realign | DOUBLE | -1.0 | mismatch penalty in target microsatellite region |
| --gap-open-penalty-realign | DOUBLE | 2.0 | gap open penalty in target microsatellite region |
| --gap-open-extension-realign | DOUBLE | 2.0 | gap extension penalty in target microsatellite region |


## DOWNLOAD

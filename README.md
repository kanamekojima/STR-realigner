# STR-realigner

## OVERVIEW

STR-realigner is a Java program that extracts and realigns sequence reads in input SAM/BAM file around prespecified short tandem repeat regions. Realigned sequence reads are saved as SAM/BAM format and used for variant calling with existing STR callers.

## INPUT

- The sequence read data in SAM or BAM format
- A list of STR regions (explanation given below)
- Reference genome such as GRCh38

## OUTPUT

Realigned sequence reads in SAM or BAM format

## BASIC USAGE

Prepare a file for STR regions for realignment with the following command:

~~~~
java -jar STR-realigner.jar \  
    RegionFinder \
    --output <STR region file for realignment>
    <Fasta file> \
    <STR region file>
  
~~~~

`<STR region file>` is given as the following format:

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

By applying the obtained `<STR region file for alignment>`, reads in `<input SAM or BAM file>` is realigned:

~~~~
java -jar STR-realigner.jar \  
    Realigner \
    --output-file <Realigned BAM file> \
    <Input SAM or BAM file> \
    <Fasta file> \
    <STR region file>
  
~~~~



## OPTIONS

### Realigner

| Option | Value Type | Default | Summary |
|--------|:-----------|:--------|:--------|
| --fusion-distance | INT | none | window distance for unifying realignment target regions |
| --help | BOOLEAN | false | print options and exit |
| --flanking-region-size | INT | 100 | flanking region size for realignment region |
| --output-file | STRING | STDOUT | output BAM file with realigned reads (SAM format text is printed to stdout without option |
| --skip-homopolymer-size | INT | 15 | homopolymer size skipped in realignment |
| --fusion-distance | INT | 80  | window distance for unifying realignment target regions |
| --match-penalty-realign | DOUBLE | -1.0 | match penalty in target microsatellite region |
| --mismatch-penalty | DOUBLE | 4.0 | mismatch penalty in target microsatellite region |
| --gap-open-penalty | DOUBLE | 6.0 | gap open penalty in target microsatellite region |
| --gap-extension-penalty | DOUBLE | 1.0 | gap extension penalty in target microsatellite region |
| --gap-open-penalty-realign | DOUBLE | 4.0 | gap open penalty in target microsatellite region |
| --gap-extension-realign | DOUBLE | 1.0 | gap extension penalty in target microsatellite region |
| --clipping-penalty | DOUBLE | 5.0 | gap extension penalty in target microsatellite region |
|--skip-realignment  | BOOLEAN | false | flag for applying realignment skip |
| --skip-realignment-base-quality N | INT | 60 | base quality score threshold for realignment skip |
| --skip-realignment-mismatch-count N | INT | 5 | mismatch base count limit for realignment skip |


### RegionFinder

| Option | Value Type | Default | Summary |
|--------|:-----------|:--------|:--------|
| --help | BOOLEAN | false | Print options and exit |
| --flanking-region-size | INT | 1 | flanking region size for analysis |
| --output-file | STRING | STDOUT | output text for region information |

## Changelog


- v0.1.01
 - New options for realignment skipping on reads satisfying some conditions were added.


## CONTACT

Developer: Kaname Kojima

kojima[AT]megabank[DOT]tohoku[DOT]ac[DOT]jp

Please replace [AT] and [DOT] with "@" and ".", respectively.


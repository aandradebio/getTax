# Taxonomic Information Retrieval Scripts

These scripts are designed to retrieve taxonomic information for protein sequences using NCBI's Entrez Utilities.

## Prerequisites

Before running the scripts, ensure that you have the following dependencies installed:

- [esearch](https://www.ncbi.nlm.nih.gov/books/NBK179288/)
- [efetch](https://www.ncbi.nlm.nih.gov/books/NBK25499/)
- [xtract](https://www.ncbi.nlm.nih.gov/books/NBK179288/)

## Usage

### `getTax.sh`

#### Description

The `getTax.sh` script retrieves taxonomic information for a given protein sequence accession number.

#### Usage

```bash
./getTax.sh [ACCESSION_NUMBER]
```

Replace [ACCESSION_NUMBER] with the desired protein sequence accession number.

Example:

```bash
./getTax.sh AAA46477.1
```

An easy way to get taxonomy info for multiple accession numbers would be creating a run.sh file.

## Usage Example

To process multiple accession numbers, you can use the `run.sh` script:

### `run.sh`

#### Description

The `run.sh` script processes a list of protein sequence accession numbers using the `getTax.sh` script.

#### Usage

1. Update `run.sh` with the desired accession numbers.
2. Execute `run.sh`.

#### Example

```bash
#!/usr/bin/bash

./getTax.sh AAA46477.1 &
./getTax.sh AAC55975.1 &
./getTax.sh AAD02414.1 &
./getTax.sh AAD47817.1 &
./getTax.sh AAF29594.1 &
./getTax.sh AAF29595.1 &
./getTax.sh AAF80604.1 &
./getTax.sh AAH69831.1 &
wait
```

The `run.sh` script can be created based on a file containing multiple accession numbers or you could use: 

```bash
while read ACC; do ./getTax.sh ${acc}; done < accession_numbers.txt
```

## Author

Amanda Araújo Serrão de Andrade aandradebio@gmail.com

Feel free to contact me, open an issue, or a pull request.






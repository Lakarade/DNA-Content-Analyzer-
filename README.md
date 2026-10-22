
# DNA Content Analyzer

A beginner-friendly Python command-line tool for analysing DNA sequences stored in FASTA format.

## Project Overview

This project reads DNA sequences from a FASTA file and calculates basic sequence statistics. It was developed to practise Python programming and apply computational methods to biological data.

## Features

- Reads DNA sequences from FASTA files.
- Supports multiple sequences in a single file.
- Calculates sequence length.
- Calculates GC content percentage.
- Calculates AT content percentage.
- Handles lowercase nucleotide sequences.
- Handles missing input files with an error message.
- Uses a reusable Python function for sequence analysis.

## Technologies Used

- Python
- FASTA file format
- GitHub

## Requirements

- Python 3 installed on your computer.
- A FASTA file containing DNA sequences.

No external Python packages are required.

## How to Run

1. Download or clone this repository.
2. Keep `dna_analyser.py` and your FASTA file in the same folder.
3. Open a terminal in that folder.
4. Run the command:

   ```bash
   python dna_analyser.py
   ```

5. When prompted, enter the FASTA filename:

   ```text
   gene.fna
   ```

6. View the sequence statistics printed in the terminal.

## Example

For the DNA sequence:

```text
>Example_Gene
ATGC
```

Expected output:

```text
Gene: >Example_Gene
Length: 4
GC%: 50.0
AT%: 50.0
```

## Methodology

1. Read the FASTA file line by line.
2. Identify sequence headers beginning with `>`.
3. Collect the nucleotide sequence associated with each header.
4. Convert the sequence to uppercase.
5. Calculate the sequence length and nucleotide composition.
6. Calculate GC and AT percentages using standard A, T, G and C bases.
7. Display the results for each sequence.

## Limitations

- Only standard DNA bases (A, T, G and C) are included in the calculations.
- Ambiguous or invalid characters are currently excluded rather than reported separately.
- The tool provides basic sequence statistics and does not perform gene identification or biological function prediction.

## Future Improvements

- Export results to a CSV file.
- Report ambiguous and invalid nucleotide characters.
- Add automated tests for different sequence types.
- Improve input validation and error handling.
- Add graphical visualisation of nucleotide composition.

## Author

Lakshita Karade

# **project1-sequence-analysis**
# Identifying Mutations in NGS Data

## Title and Purpose
This project uses Python to analyse DNA sequencing reads (Next Generation Sequencing) from fission yeast (_S.pombe_). It looks for differences between the reads and a reference sequence and compares treated samples with untreated control samples.

## How to Run the Program
The program is in a Google Colab notebook. Open the notebook in Colab and run the setup cells first, followed by the projects functions and then the final analysis cells in order of how they are presented.

## Inputs and Outputs
The program takes a 200 nucleotide reference sequence and a CSV file containing 6,000 sequencing reads from six samples. Each read includes a read ID, sample, group and DNA sequence. The outputs include valid and invalid reads, mismatch percentages, substitution counts (sub) and the positions with the most mismatches. It also compares the treatment and control groups using Welch's t-test.

## Code Design
The program is split into five functions so that each one has a different role. For example, validate_read() checks the sequences, while find_mutations() identifies differences from the reference. This makes it easier to understand and test.

I used dictionaries to keep information about each read and sample together. This makes it easier to access values using clear names such as the number of valid reads and mismatch positions. Dictionaries make information easier to organise.

The invalid reads were also kept in the results instead of removing them. This means that can be counted and reported, but excluded from mismatch calculations. In Step 5, I used a list to include every reference position, even the ones with no mismatches, rather than storing only positions where mutations occurred.

## Testing
The three informative tests were:
1. Using smaller example datasets as well as the full dataset. Checked that lowercase sequences converted to uppercase and the incorrect lengths and invalid characters were detected.
2. Tested Step 4 using a small dataset that was tested with invalid and valid reads, checking that mismatch counts and percentages wee correct.
3. Tested Step 5 using a small dataset where top positions and group averages could be checked with known mismatch positions.

Each step passed!

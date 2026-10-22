
def analyze_sequence(sequence):
    """Calculate basic statistics for a DNA sequence."""

    # Standardise the sequence to uppercase
    sequence = sequence.upper()

    # Count only the four standard DNA bases
    valid_bases = "ATGC"
    clean_sequence = ""

    for base in sequence:
        if base in valid_bases:
            clean_sequence += base

    # Calculate sequence length
    length = len(clean_sequence)

    # Avoid division by zero
    if length == 0:
        return {
            "length": 0,
            "gc_percent": 0.0,
            "at_percent": 0.0
        }

    # Count G and C bases
    g_count = clean_sequence.count("G")
    c_count = clean_sequence.count("C")

    # Count A and T bases
    a_count = clean_sequence.count("A")
    t_count = clean_sequence.count("T")

    # Calculate percentages
    gc_percent = (g_count + c_count) / length * 100
    at_percent = (a_count + t_count) / length * 100

    # Return the results
    return {
        "length": length,
        "gc_percent": gc_percent,
        "at_percent": at_percent
    }


# Ask the user for a FASTA filename
file_name = input("Enter FASTA file name: ")

try:
    with open(file_name, "r") as file:
        current_header = ""
        current_sequence = ""

        for line in file:
            line = line.strip()

            # A FASTA header starts with >
            if line.startswith(">"):

                # Process the previous sequence
                if current_header:
                    results = analyze_sequence(current_sequence)

                    print("\nGene:", current_header)
                    print("Length:", results["length"])
                    print("GC%:", round(results["gc_percent"], 2))
                    print("AT%:", round(results["at_percent"], 2))

                # Start a new sequence
                current_header = line
                current_sequence = ""

            else:
                # Ignore blank lines
                current_sequence += line

        # Process the final sequence
        if current_header:
            results = analyze_sequence(current_sequence)

            print("\nGene:", current_header)
            print("Length:", results["length"])
            print("GC%:", round(results["gc_percent"], 2))
            print("AT%:", round(results["at_percent"], 2))

except FileNotFoundError:
    print("Error: File not found. Check the filename and try again.")

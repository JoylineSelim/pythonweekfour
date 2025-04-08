# pythonweekfour

def modify_and_write_file(input_filename, output_filename):
    """
    Reads a file, modifies each line, and writes the modified lines to a new file.

    Args:
        input_filename: The name of the input file.
        output_filename: The name of the output file.
    """
    try:
        with open(input_filename, 'r') as infile, open(output_filename, 'w') as outfile:
            for line in infile:
                # Modify each line (example: add "MODIFIED: " at the beginning)
                modified_line = "MODIFIED: " + line
                outfile.write(modified_line)

        print(f"File '{input_filename}' modified and written to '{output_filename}' successfully.")

    except FileNotFoundError:
        print(f"Error: File '{input_filename}' not found.")
    except IOError as e:  # Catch other input/output errors
        print(f"Error: Could not read or write file. {e}")
    except Exception as e:
        print(f"An unexpected error occurred: {e}")

def get_filename_and_process():
    """
    Asks the user for a filename and handles errors if it doesn't exist or can't be read.
    """
    input_filename = input("Enter the input filename: ")
    output_filename = input("Enter the output filename: ")

    modify_and_write_file(input_filename, output_filename)

# Run the function to get filename and process the files.
get_filename_and_process()

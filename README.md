# Week4Assignment
def modify_file(input_filename, output_filename):
    try:
        # Read the input file
        with open(input_filename, 'r') as input_file:
            content = input_file.read()
        
        # Modify the content (example: convert to uppercase and add line numbers)
        modified_lines = []
        lines = content.split('\n')
        for i, line in enumerate(lines, 1):
            modified_line = f"{i}. {line.upper()}"
            modified_lines.append(modified_line)
        
        modified_content = '\n'.join(modified_lines)
        
        # Write to the output file
        with open(output_filename, 'w') as output_file:
            output_file.write(modified_content)
        
        print(f"File successfully modified and saved as {output_filename}")
    
    except FileNotFoundError:
        print(f"Error: The file {input_filename} was not found.")
    except Exception as e:
        print(f"An error occurred: {str(e)}")



        #Error Handling
def read_file_safely():
    while True:
        filename = input("Enter the filename to read: ").strip()
        
        try:
            # Try opening and reading the file
            with open(filename, 'r') as file:
                content = file.read()
            
            print("\nFile content:")
            print("-------------")
            print(content)
            break  # Exit loop if successful
        
        except FileNotFoundError:
            print(f"Error: The file '{filename}' does not exist. Please try again.")
        except PermissionError:
            print(f"Error: You don't have permission to read '{filename}'. Try another file.")
        except UnicodeDecodeError:
            print(f"Error: Could not decode '{filename}'. It may be a binary file.")
        except Exception as e:
            print(f"An unexpected error occurred: {str(e)}")









        


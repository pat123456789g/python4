# python4
def read_and_modify_file():
    try:
        # Ask the user for the filename
        filename = input("Enter the filename to read: ")
        
          # Open the file for reading
        
          with open(filename, "r") as file:
              content = file.readlines()  # Read all lines
  
          # Modify the content (Example: Add line numbers)
          modified_content = [f"{i+1}: {line}" for i, line in enumerate(content)]
  
          # Create a new filename for the modified file
          new_filename = "modified_" + filename
  
          # Write the modified content to a new file
          with open(new_filename, "w") as new_file:
              new_file.writelines(modified_content)
  
          print(f"Modified file saved as: {new_filename}")
  
      except FileNotFoundError:
          print("Error: The file does not exist. Please check the filename and try again.")
      except PermissionError:
          print("Error: Permission denied. You don’t have access to read this file.")
      except Exception as e:
          print(f"An unexpected error occurred: {e}")

# Run the function
read_and_modify_file()

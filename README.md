# Exercise 5: Copy and Rename Files  

### Reg No: 212221040013

## AIM:
To copy all files from a source folder to a destination folder and rename them by appending a timestamp to the file names.

## Activities Required:
  1. Assign
  2. For Each
  3. Copy File

## Procedure:
  1. Open **UiPath Studio** and create a new process called **CopyAndRenameFiles**.
    
  2. Create variables for the source folder, destination folder, file names, and timestamp: sourceFolder (Type: String), destinationFolder (Type: String), fileNames (Type: IEnumerable<String>), newFileName (Type: String), timestamp (Type: String).
    
  3. Use an **Assign** activity to set the paths of the source and destination folders: sourceFolder = "C:\SourceFolder" and destinationFolder = "C:\DestinationFolder".
    
  4. Use an **Assign** activity to get the list of files: fileNames = Directory.GetFiles(sourceFolder).
    
  5. Use a **For Each** activity to loop through each file in fileNames with TypeArgument set to String.
    
  6. Inside the **For Each** loop, use an **Assign** activity to extract the file name and extension: fileName = Path.GetFileName(item) and fileExtension = Path.GetExtension(item).
    
  7. Use an **Assign** activity to generate a timestamp to append to the file name: timestamp = Now.ToString("yyyy-MM-dd_HH-mm-ss").
    
  8. Use an **Assign** activity to create the new file name with the timestamp: newFileName = Path.GetFileNameWithoutExtension(item) + "_" + timestamp + fileExtension.
    
  9. Use a **Copy File** activity to copy and rename the file: set Path to item and Destination to Path.Combine(destinationFolder, newFileName).
    
  10. Run the workflow to copy and rename all files from the source folder to the destination folder.

## Workflow:
![image](https://github.com/user-attachments/assets/7988d276-2120-4025-8735-1886b0cb06d3)

## Output:
![image](https://github.com/user-attachments/assets/ae1fa143-8905-4d0b-b787-f832bf5e6aed)

## Result:
Thus, all files are successfully copied and renamed in the destination folder without overwriting existing files.

# File-Integrity-Monitoring-System

File Integrity Monitooring System can be used to **detect whether tampering is done with a directory and files inside using a graphical interface**.

This File Integrity Monitoring System is developed using Python programming.

### Modules Used in Implementation : 
- `OS module` : This module is used for interacting with the file system tree.
- `Hashlib module` : SHA512 function is used from this module.
- `tkinter module` : This module helped in making the GUI more presentable.
- `glob module` : This module is used to return all file paths that match a specific pattern.


## Function's of File Integrity Monitoring System : 

1. **`Browsing a Directory`** :  When clicked on the 'Browse' button, File Integrity Monitoring System prompts a window that allows the users to select a directory.

2. **`Updating Baseline`** : When clicked on the 'Update Baseline', 
                          File Integrity Monitoring System first checks whether a directory was selected through the 'Browse' button, if not then a message saying - "Directory not selected" is prompted, else a baseline file is created/updated for the browsed directory. Baseline stores paths of all the files in the directory and calculates SHA512 hash from the respective files contents and stores in the following format :

      - FilePath1 = Hash1
  
      - FilePath2 = Hash2
  
      - FilePath3 = Hash3
      
 Example :
  ```
   C:\Users\Yash\Desktop\Files\text.docx = sdfde4sfddfsdfd6d915eb037936863a841675f93225c279fad6954sdfdsfc66fcbcd31sddsffsdfbce78ae7dfa2160f8920d0b967af2b7030
  ```
  
 3. **`Checking Integrity`** : When clicked on the 'Check Integrity' button,
                        File Integrity Monitoring System first checks whether a directory was selected through the Browse button, 
                         if not then a message saying - "Directory not selected" is prompted,
                         But if selection was done, 
                          then, it checks whether baseline for selected directory exists or not. 
                          If baseline exists, it then cross checks with the baseline and tells the files in which data was changed. It also tells which files were added and removed after the last update of baseline.
                          But if baseline doesn't exists, then it displays an error message saying- "Baseline file not present".
                          (NOTE : Baseline file is necessary for comparison of file's present content to a known trusted state.)
 
 ## Key Features about File Integrity Monitoring System : 
 
 - File Integrity Monitoring System uses the idea of comparing the file’s current state hash with the hash stored in the established baseline. 
 - File Integrity Monitoring System is capable of monitoring all types of files viz. .doc, .txt, .rtf, .ppt, .xlxs
 - When a directory is being monitored, HashLine works fine with subdirectories i.e.
    -  It updates baseline with files in subdirectories.
    -  Also checks integrity of files in subdirectories.
 - File Integrity Monitoring System can also check integrity of different directories, as separate baseline is maintained for each directory.

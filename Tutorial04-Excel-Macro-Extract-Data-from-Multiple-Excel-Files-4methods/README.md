# Excel Macro

Tutorial on how to extract data from multiple Excel files that are in a specific folder into a single workbook using Macro/VBA.

The extracted data can be collected into single or multiple sheets of that workbook.

Use master_file-singlesheet-0.xlsm as initial file for the tutorial.

Let’s say we have multiple Excel files in a folder in our computer storage. In this case, we’ve created a folder named saledata in the Local Directory to hold the Excel files.

The Excel files contain sale data for 5 consecutive days for a bike shop. For example, in the file named Day1.xlsx, we have the sale details of the products of the date 1/1/2023.

We want to extract these sale data from the Excel files of the folder and collect them into one single file that must be in **another location** other than *this folder*.

## Prerequisite:

In the macro, **FileSystemObject** is an object to access our local computer’s file system to get the files inside the folder.

Folder path must be adjusted correctly to get access the Excel files in it.

**For Each Next loop** is used to loop through all the Excel files inside the folder.

**For Next Loop** is used to extract data from the source files and paste them to the new file.

### Write Code in Visual Basic Editor

To extract data from multiple Excel files to a new workbook, we’ll use several VBA functions and properties in our code.

The following section describes how to open and write code in the visual basic editor:

- Right-click on the sheet name.
- Choose the View Code option.
- Now put your macro in the visual basic editor.
- Press F5 to run the code.


## Method 1: Run a Macro to Extract Data from Multiple Excel Files to a Single Workbook

Collect the Extracted Data into Different Worksheets: Refer to master_file-singlesheet-1a.xlsm

Extract Data into a Single Worksheet: Refer to master_file-singlesheet-1b.xlsm

## Method 2: Extract and Then Merge Data from Multiple Excel Files to a Single File Using a Marco

We’ll extract data from different files and merge them into one file.

As every dataset in the files in the folder has a header, we’ll keep the header only for the first file.

This will produced mergeFiles with only a single header as seen in master_file-singlesheet-2.xlsm.

Let’s copy and paste the following macro into the visual basic editor.

Refer to master_file-singlesheet-2.xlsm

## Method 3: Set Range to Extract Data from Multiple Files to a Single Workbook Using a Macro in Excel

The following macro facilitates us to choose the range of data that we want to extract from the dataset into a new workbook.

In this example, we want to extract only the first two rows of data from each of the Excel files.

To accomplish this, we need to set the range as A1:E3 in the following macro.

As the output, we’ve extracted only two rows of data from the dataset of each source files to the newly created worksheet.

Set your own data range in the following line of the macro:

```visual
Set srcRng = .Range("A1:E3")
```


Refer to master_file-singlesheet-3.xlsm

## Method 4: Extract Data from Selected Files into One Workbook Using Macro in Excel

We’ve configured the previous macro so that we can choose Excel files from the file explorer.

This way we can specify the source files to extract data from.

Let’s say we want to select and extract data only from 1st 3 files in the folder.

The source code produce this error for 64 Bit machines:

```bash
Microsoft Visual Basic for Applications
Compile error:
!
The code in this project must be updated for use on 64-bit
systems. Please review and update Declare statements and
then mark them with the PtrSafe attribute.
```

The solution is to add the PtrSafe keyword to the Declare statement as seen in:

Refer to master_file-singlesheet-4.xlsm



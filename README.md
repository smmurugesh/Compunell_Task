# Compunell_Task
Interview Programming Exercise for Planet

HOW TO INVOKE THE PROGRAM

Step 1: Install the latest Java runtime environment available at https://java.com/en/download/
Step 2: Copy the "Murugesh_CompunnelInterviewProgram.jar from GIT repo to your desktop.
Step 3: Double click the jar file and it should open up the command prompt. 
Step 4: Follow the instructions on the screen to supply input file path. Sample input files attached in email.

IF DOUBLE CLICKING DID NOT OPEN THE COMMAND PROMPT, TRY ONE OF THE TWO METHODS BELOW:

METHOD 1:
Step 1: Right click on your Start button and do a search for “regedit”, then open it.
Step 2: Now expand the HKEY_CLASSES_ROOT folder, and scroll down until you find the folders “jar_auto_file” or "jarfile"
Step 3: Expand "jar_auto_file" or "jarfile" > Shell > Open > Command.
Step 4: You will see a key named “Default”. Right click on “Default” and choose “Modify”.
Step 5: Now in the “Value data” box, replace the C:\Program Files\etc with your actual Java installation folder, for example mine is C:\Program Files (x86)\Java\jre1.8.0_221\bin\java.exe
Step 6: Final value will like this --> "C:\Program Files (x86)\Java\jre1.8.0_221\bin\javaw.exe" -jar "%1" %*and press OK.
Step 7: Double click the jar file now and it should open up the command prompt. 
Step 8: Follow the instructions on the screen to supply input file path. Sample input files attached in email.

METHOD 2:
Step 1: Right click on your Start button and do a search for "cmd", then open it.
Step 2: In command prompt, Go to the desktop path where you copied the jar by using cd command
Example: C:\Users\Murugesh\Desktop>
Step 3: Run this command --> java -jar Murugesh_CompunnelInterviewProgram.jar
Step 4: Follow the instructions on the screen to supply input file path. Sample input files attached in email.


CONTENT EXPLAINATION:
1) jar folder has the executable jar of this project
2) Samples folder has the input and output files for reference

Totally this java project comprises of 6 classes.

CompunellMain.java
- Main class for this jar.
- It prompts user to provide the location of Inputfile for processing.
- As per requirement, only text files are accepted.
- The format of the input file could be either one of the two formats specified below. The input file will contain a file format code (1 or 2) on the first line and a sequence of records, with one record per line
- You can type 0 anytime to exit the program.
- Once user provides a valid path of input file, program checks the format code present in first line.
- Depending on the format code present in Input file, Program invokes the correct implementaion class of the abstract class EmployeeFile.
- Implentation class reads the lines in InputFile and parse them to a list of Employee objects.
- List is sorted and contents of the each employee Object is printed to a output file as per the layout provided in requirement.
- Output file is created in same location as that of Input file.

Employee.java
- Java object to hold employee information
- It implements a Comparable Interface, So that a collection of Employee objects can be sorted.
- As per the requirement, Employee records will be sorted ascending by their First Name, Last Name and Start Date.

EmployeeFile.java
- Abstract class defined with constants and the sequence order of Employee elements presnet in the Input file.
- If the sequence order for elements is changed in input file, its enough to change the ordering in this class.
- It has abstract method parseFile(), whose implementation is defined in the classes FixedLengthFile and CommaSeparatedFile.
- createEmployeeObject method validates the elements of the record in input file, Throw message to user appropriately. If no issues in record, then creates Employee object.

FixedLengthFile.java
- As per requirement, default length is defined as 80
- A HashMap contains the element label as key and length as value. Length is defined as provided in the requirement.
- Position of each element in the input file record is dynamically obtained from the sequence order of elements and length of the element.
- For any change in the length of element requires only the HashMap to be updated.
- parseFile() method is implemented.

DelimiterSeparatedFile.java
- As per requirement, default delimiter is defined as comma
- Validates the number of elements in a record is matching the element list size, Since commas will be present as place holders for absent elements.
- delimiter comma can be overwritten as well if file delimiter is updated.
- parseFile() method is implemented based.

Util.java
- Has utility method to find whethere the give file path is valid.
- Has utility method to get the file extension.
- Has utility method to validate Numeric, alphabets and alphanumerics




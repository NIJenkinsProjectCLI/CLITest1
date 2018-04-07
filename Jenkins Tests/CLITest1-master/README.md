# CLITest1
This is for learning how to use GitHub with LabVIEW 2018 CLI and Jenkins


Mass Compile via CLI (Current Instructions):
1. Win+R > cmd > Enter #Brings up command line
2. LabVIEWCLI -OperationName MassCompile -DirectoryToCompile "C:\Users\Aaron\Desktop\Jenkins Tests\CLITest1-master"
3. Enter 

Expected Output:
LabVIEWCLI started logging in file:  C:\Users\Aaron\AppData\Local\Temp\lvtemporary_814460.log
"LabVIEWPath" command line argument is not passed. Using last used LabVIEW: "C:\Program Files (x86)\National Instruments\LabVIEW 2018\LabVIEW.exe"
Connection established with LabVIEW at port number 3363.

Operation output: 
#### Starting Mass Compile: Sat, Apr 7, 2018 9:42:31 AM
  Directory: "C:\Users\Aaron\Desktop\Jenkins Tests\CLITest1-master"
#### Finished Mass Compile: Sat, Apr 7, 2018 9:42:31 AM

MassCompile operation succeeded.

Syntax:
LabVIEWCLI -OperationName MassCompile -DirectoryToCompile <path of directory to mass compile>
[-MassCompileLogFile <mass compile log file path>] [-AppendToMassCompileLog <TRUE or FALSE>]
[-NumberOfVIsToCache <numeric value>] [-ReloadLVSBs <true or false>]
Arguments Description:
• -DirectoryToCompile: [Required]: Specifies the directory where the mass compile should begin.
• -MassCompileLogFile: [Optional]: Specifies a file path where results of the mass compile should be placed.
• -AppendToMassCompileLog: [Optional]: <True or False>. Specifies whether results should be appended to the log file. Default value is FALSE.
• -NumOfVIsToCache: [Optional]: Specifies the number of VIs that should be allowed to remain in memory during the mass compile. Default value is 0.
• -ReloadLVSBs: [Optional]: If TRUE, causes CINs in VIs to be ignored and the application to search for them. Useful when a large number of CINs have been recompiled and need to be reloaded. Default value is FALSE.

Example:
LabVIEWCLI -OperationName MassCompile -DirectoryToCompile "C:\temp" -MassCompileLogFile
"C:\temp\log.txt" -AppendToMassCompileLog true -NumOfVIsToCache 0 -ReloadLVSBs false

Execute LabVIEW Build Specification via CLI (Current Instructions):
1. Win+R > cmd > Enter #Brings up command line
2. LabVIEWCLI -OperationName ExecuteBuildSpec -ProjectPath "C:\Users\Aaron\Desktop\Jenkins Tests\CLITest1-master"
3. Enter

Expected Output:
LabVIEWCLI started logging in file:  C:\Users\Aaron\AppData\Local\Temp\lvtemporary_948969.log
"LabVIEWPath" command line argument is not passed. Using last used LabVIEW: "C:\Program Files (x86)\National Instruments\LabVIEW 2018\LabVIEW.exe"
Connection established with LabVIEW at port number 3363.

Operation output: 
Generated files are:
C:\Users\Aaron\Desktop\Jenkins Tests\CLITest1-master\builds\build1\TestingBuildSpecs.exe
C:\Users\Aaron\Desktop\Jenkins Tests\CLITest1-master\builds\build1\TestingBuildSpecs.aliases
C:\Users\Aaron\Desktop\Jenkins Tests\CLITest1-master\builds\build1\TestingBuildSpecs.ini

ExecuteBuildSpec operation succeeded.

Syntax:
LabVIEWCLI -OperationName ExecuteBuildSpec -ProjectPath <path of LabVIEW project>
[-BuildSpecName <name of the build specification>] [-TargetName <name of the target>]
Arguments Description:
• -ProjectPath: [Required]: Specifies the full path to the LabVIEW project (.lvproj) file that contains
the build specification.
• -BuildSpecName: [Optional]: Specifies the name of the build specification. Enter the name that
appears under Build Specifications in the Project Explorer window to specify which build
specification builds. If you do not specify a build specification, the LabVIEWCLI builds all build
specifications under the specified target by default.
• -TargetName: [Optional]: Specifies the target that contains the build specification. The target is
"My Computer" by default.
Example:
LabVIEWCLI -OperationName ExecuteBuildSpec -ProjectPath "C:\temp\test.lvproj" -TargetName "My
Computer" -BuildSpecName "My DLL"

Run VI Analyzer via CLI(Current Instructions):
1. Win+R > cmd > Enter #Brings up command line
2. LabVIEWCLI -OperationName RunVIAnalyzer -ConfigPath <path of VI Analyzer configuration file>
-ReportPath <Path of VI Analyzer report file>

***Challenges and Errors***
Error 85 - LabVIEW: (Hex 0x55) Scan failed. The input string does not contain data in the expected format.

Syntax:
LabVIEWCLI -OperationName RunVIAnalyzer -ConfigPath <path of VI Analyzer configuration file>
-ReportPath <Path of VI Analyzer report file> [-ReportSaveType <format of report file>]
[-ConfigPassword <password of config file>]
Arguments Description:
• -ConfigPath: [Required]: Specifies the path to the configuration file (.cfg) that contains VI Analyzer
task settings to use in the analysis. You can use a configuration file you saved through the VI
Analyzer or the VI Analyzer VIs. Alternatively, you can specify a VI, folder, or LLB to analyze. If you
specify an item other than a configuration file, the VI runs all VI Analyzer tests on the specified
item.
• -ReportPath: [Required]: Specifies the path to the report or results file.
• -ReportSaveType: [Optional]: Specifies the format of the report or results file. This can be either
a tab-delimited ASCII file, an HTML file, or a VI Analyzer results file (.rsl). The default is an ASCII
file. If you select RSL File, the VI saves the report data to a VI Analyzer results file that you can load
into the VI Analyzer Results Window.
• -ConfigPassword: [Optional]: Specifies the password for the configuration file if any.
Example:
LabVIEWCLI -OperationName RunVIAnalyzer -ConfigFilePath "C:\temp\test.cfg" -ReportPath
"C:\temp\output.html" -ReportSaveType "html" -ConfigPassword "abc"

Run UTF Tests via CLI (Current Instructions):
1. Win+R > cmd > Enter #Brings up command line
2. LabVIEWCLI -OperationName RunUnitTests -ProjectPath "C:\Users\Aaron\Desktop\Jenkins Tests\CLI Test Project.lvproj" -JUnitReportPath "C:\Users\Aaron\Desktop\Jenkins Tests\UTF Output.xml"
3. Enter

Expected Output:
LabVIEWCLI started logging in file:  C:\Users\Aaron\AppData\Local\Temp\lvtemporary_290289.log
"LabVIEWPath" command line argument is not passed. Using last used LabVIEW: "C:\Program Files (x86)\National Instruments\LabVIEW 2018\LabVIEW.exe"
Connection established with LabVIEW at port number 3363.

Operation output: 
1 tests path passed.
0 tests path failed.
0 tests path errored.
0 tests path skipped.
0 tests path not processed.
Please find the JUnit report path at "C:\Users\Aaron\Desktop\Jenkins Tests\UFT Output.xml".
RunUnitTests operation succeeded.



***Challenges and Errors***
Error -350051 occurred at an unidentified location
Possible reason(s):
LabVIEW CLI: (Hex 0xFFFAA89D) The CLI for LabVIEW failed to run the operation because the command contains illegal arguments.
Resolution: Used LabVIEW 2018 syntax from http://labview.natinst.com/docs/proposals/2018/LabVIEW%20CLI/index.html

Syntax: **Updated**
LabVIEWCLI -OperationName RunUnitTests -ProjectPath <project file path> -JUnitReportPath <output file
path>
Arguments Description:
• -ProjectPath: [Required]: Project file path/ Test file path.
• -JUnitReportPath: [Required]: Output JUnit file path.
Example:
LabVIEWCLI -OperationName RunUnitTests -ProjectPath "C:\temp\test.lvproj" -JUnitReportPath
"C:\temp\test.xml"


Close LabVIEW via CLI (Current Instructions):
1. Win+R > cmd > Enter #Brings up command line
2. LabVIEWCLI -OperationName CloseLabVIEW
3. Enter


***Challenges and Errors***
Error -350000 occurred at an unidentified location
Possible reason(s):
LabVIEW CLI: (Hex 0xFFFAA8D0) The CLI for LabVIEW failed to establish a connection with LabVIEW. Ensure LabVIEW is running with VI server enabled on the correct port number. To enable VI server in LabVIEW, select "Tools>>Options>>VI Server" and enable the "TCP/IP" checkbox. If the port number under "TCP/IP" is not 3363, you must specify the port number using the "-PortNumber" argument.


Syntax:
LabVIEWCLI -OperationName CloseLabVIEW
Arguments Description:
None
Example:
LabVIEWCLI -OperationName CloseLabVIEW

Run VI via CLI (Current Instructions):
1. Win+R > cmd > Enter #Brings up command line
2. LabVIEWCLI -OperationName RunVI -VIPath "C:\Users\Aaron\Desktop\Jenkins Tests\CLITest1-master\Run VI Test Alyssa.vi"
3. Enter

Expected Output:
LabVIEWCLI started logging in file:  C:\Users\Aaron\AppData\Local\Temp\lvtemporary_29571.log
"LabVIEWPath" command line argument is not passed. Using last used LabVIEW: "C:\Program Files (x86)\National Instruments\LabVIEW 2018\LabVIEW.exe"
Connection established with LabVIEW at port number 3363.

Operation output: 
Yay! It ran!
RunVI operation succeeded.

Syntax:
LabVIEWCLI -OperationName RunVI -VIPath <VIPath> <Argument1> <Argument2> ...
Arguments Description:
• -VIPath: [Required]: VI path.
• Command line arguments for the VI: [Optional]: Command line arguments for the VI to run.
Example:
LabVIEWCLI -OperationName RunVI -VIPath "C:\DemoProject\Add.vi" 101 202



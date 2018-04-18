node{
  bat '''echo Pizza
LabVIEWCLI -OperationName MassCompile -DirectoryToCompile "C:\\Users\\Aaron\\Desktop\\Jenkins Tests\\CLITest1-master"
LabVIEWCLI -OperationName RunUnitTests -ProjectPath "C:\\Users\\Aaron\\Desktop\\Jenkins Tests\\CLI Test Project.lvproj" -JUnitReportPath "C:\\Users\\Aaron\\Desktop\\Jenkins Tests\\UTF Output.xml"
LabVIEWCLI -OperationName ExecuteBuildSpec -ProjectPath "C:\\Users\\Aaron\\Desktop\\Jenkins Tests\\CLITest1-master\\TestingBuildSpec.lvproj"
echo Did it work? Yes it did. Press ENTER to close LabVIEW
LabVIEWCLI -OperationName CloseLabVIEW'''
}


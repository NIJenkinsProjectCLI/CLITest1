node{
 stage('Pull_from_GitHub') {
       git url: "https://github.com/NIJenkinsProjectCLI/CLITest1", branch: "master"
 }
 stage('RunVI') {
       bat 'LabVIEWCLI -OperationName RunVI -VIPath \"C:\\Users\\Aaron\\Desktop\\Jenkins Project\\workspace\\sProjectCLI_CLITest1_master-MZ36JFLZGKJ4ACFPZWKCUWIVS7AQXG3FOPB7P2U7VEFXNUF5XLVQ\\Run VI Test.vi" 8 5672'
 }
 stage('Mass_Compile_VI_Project') {
       bat 'LabVIEWCLI -OperationName MassCompile -DirectoryToCompile \"C:\\Users\\Aaron\\Desktop\\Jenkins Project\\workspace\\sProjectCLI_CLITest1_master-MZ36JFLZGKJ4ACFPZWKCUWIVS7AQXG3FOPB7P2U7VEFXNUF5XLVQ"'
 }
 stage('Unit_Framework_Tests') {
       bat 'LabVIEWCLI -OperationName RunUnitTests -ProjectPath \"C:\\Users\\Aaron\\Desktop\\Jenkins Project\\workspace\\sProjectCLI_CLITest1_master-MZ36JFLZGKJ4ACFPZWKCUWIVS7AQXG3FOPB7P2U7VEFXNUF5XLVQ\\Jenkins Tests\\CLI Test Project.lvproj" -JUnitReportPath \"C:\\Users\\Aaron\\Desktop\\Jenkins Project\\workspace\\sProjectCLI_CLITest1_master-MZ36JFLZGKJ4ACFPZWKCUWIVS7AQXG3FOPB7P2U7VEFXNUF5XLVQ\\Jenkins Tests\\UTF Output.xml"'
 }
 stage('Run_VI_Analyzer') {
       bat 'LabVIEWCLI -OperationName RunVIAnalyzer -ConfigPath \"C:\\Users\\Aaron\\Desktop\\Jenkins Project\\workspace\\sProjectCLI_CLITest1_master-MZ36JFLZGKJ4ACFPZWKCUWIVS7AQXG3FOPB7P2U7VEFXNUF5XLVQ\\VIAnalyzerConfigFile.viancfg" -ReportPath \"C:\\Users\\Aaron\\Desktop\\Jenkins Project\\workspace\\sProjectCLI_CLITest1_master-MZ36JFLZGKJ4ACFPZWKCUWIVS7AQXG3FOPB7P2U7VEFXNUF5XLVQ\\Run VI Analyzer Results.txt"'
 }
 stage('Execute_Build_Spec'){
       bat 'LabVIEWCLI -OperationName ExecuteBuildSpec -ProjectPath \"C:\\Users\\Aaron\\Desktop\\Jenkins Project\\Build exe.lvproj" '
  //include release version?
 }
 //stage('Run EXE'){
 //      bat 'START C:\\Users\\Aaron\\Desktop\\builds\\"Build exe"\\"Test lahnbvglidfnb"\\"Test ACD Application.exe"'
// }
 //stage('Create New Release'){
 //      bat 
 //}
 stage('Close LabVIEW'){
       bat 'LabVIEWCLI -OperationName CloseLabVIEW '
 }
}

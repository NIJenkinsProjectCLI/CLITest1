node{
 stage('Pull_from_GitHub') {
       git url: "https://github.com/NIJenkinsProjectCLI/CLITest1", branch: "master"
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
  stage('RunVI') {
       bat 'LabVIEWCLI -OperationName RunVI -VIPath \"C:\\Users\\Aaron\\Desktop\\Jenkins Project\\workspace\\sProjectCLI_CLITest1_master-MZ36JFLZGKJ4ACFPZWKCUWIVS7AQXG3FOPB7P2U7VEFXNUF5XLVQ\\Run VI Test.vi" 8 5672'
 }
 stage('Execute_Build_Spec'){
       bat 'LabVIEWCLI -OperationName ExecuteBuildSpec -ProjectPath \"C:\\Users\\Aaron\\Desktop\\Jenkins Project\\Build exe.lvproj" '
 }
 //stage('Run EXE'){
 //      bat 'START C:\\Users\\Aaron\\Desktop\\builds\\"Build exe"\\"Test lahnbvglidfnb"\\"Test ACD Application.exe"'
// }
 stage('Create New Release'){
       bat 'C:\\github-release\\github-release.exe release --security-token 05cd8ec0dc1e92d56eee36a418e8f9bebe9ace12 --user "NIJenkinsProjectCLI" --repo "CLITest1" --tag "v2.0" --name "Release 5/10/18"'
 }
 stage('Close LabVIEW'){
       bat 'LabVIEWCLI -OperationName CloseLabVIEW '
 }
}

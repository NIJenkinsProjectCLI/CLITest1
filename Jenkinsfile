node{
 stage('Pull_from_GitHub') {
       //git url: "https://github.com/NIJenkinsProjectCLI/CLITest1", branch: "master"
 }
 stage('RunVI') {
       bat 'LabVIEWCLI -OperationName RunVI -VIPath \"C:\\Users\\Aaron\\Desktop\\Jenkins Project\\workspace\\sProjectCLI_CLITest1_master-MZ36JFLZGKJ4ACFPZWKCUWIVS7AQXG3FOPB7P2U7VEFXNUF5XLVQ\\FirstRunTest.vi" 204 123" '
 }
 stage('Mass_Compile_VI_Project') {
       bat 'LabVIEWCLI -OperationName MassCompile -DirectoryToCompile \"C:\\Users\\Aaron\\Desktop\\Jenkins Project\\workspace\\sProjectCLI_CLITest1_master-MZ36JFLZGKJ4ACFPZWKCUWIVS7AQXG3FOPB7P2U7VEFXNUF5XLVQ"'
 }
}
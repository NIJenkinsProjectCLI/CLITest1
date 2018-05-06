node{
 stage('Pull_from_GitHub') {
       git url: "https://github.com/NIJenkinsProjectCLI/CLITest1", branch: "master"
 }
 stage('RunVI') {
       bat 'LabVIEWCLI -OperationName RunVI -VIPath "C:\\Users\\Aaron\\Desktop\\Jenkins Project\\workspace\\sProjectCLI_CLITest1_master-MZ36JFLZGKJ4ACFPZWKCUWIVS7AQXG3FOPB7P2U7VEFXNUF5XLVQ\\RunVITest.vi" 208 456'
 }
 stage('Mass_Compile_VI_Project') {
       //bat 'LabVIEWCLI -OperationName MassCompile -DirectoryToCompile \"C:\\Users\\Aaron\\Desktop\\Jenkins Project\\workspace\\sProjectCLI_CLITest1_master-MZ36JFLZGKJ4ACFPZWKCUWIVS7AQXG3FOPB7P2U7VEFXNUF5XLVQ"'
 }
 stage('Unit_Framework_Tests') {
  //unit frame test
 }
 stage('Run_VI_Analyzer') {
  //Run VI Analyzer
 }
 stage('Execute_Build_Spec'){
  //build spec
  //include release version?
 }
}

@NonCPS
def uploadedFile = 'test.txt'

//file is uploaded to $JENKINS_HOME/$PATH_TO_THE_JOB/build/$BUILD_ID
def masterFilePath = input message: 'Upload your archive', parameters: [file(description: 'archive', name: uploadedFile)]

node('docker') { 
    stage('Copy From Master') {
        def localFile = getContext(hudson.FilePath).child(uploadedFile)
         localFile.copyFrom(masterFilePath)
        //  sh 'ls -al'
        // sh 'eval $(test.txt)'
         sh 'cat test.txt'
         }
}

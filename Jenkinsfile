pipeline {
  agent any
  triggers { pollSCM('* * * * *') }
  stages {
    stage('build') {
      steps {
	writeFile file: "application.sh", text: "echo Built ${BUILD_ID} of ${JOB_NAME}"
	archiveArtifacts artifacts: '*.sh', fingerprint: true
	echo "build successful for JAS-489"
	//sleep 60
	//error("Build failed")
      }
    }
  }
}

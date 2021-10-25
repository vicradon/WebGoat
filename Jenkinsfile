pipeline {
  agent none
  environment {
    SEMGREP_RULES = "p/security-audit p/secrets"
  }
  stages {
    stage('scan') {
      agent {
        docker { 
          image 'returntocorp/semgrep-agent:v1'
          args "-v ${WORKSPACE}:/src"
        }
      }
      steps {
        sh 'env | sort'
        sh 'semgrep-agent'
      }
    }
  }
}
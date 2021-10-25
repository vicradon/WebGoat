pipeline {
  agent any
  environment {
    SEMGREP_RULES = "p/security-audit p/secrets"
  }
  stages {
    stage('scan') {
      steps {
        sh 'env | sort'
        sh "docker run returntocorp/semgrep-agent:v1 semgrep-agent"
      }
    }
  }
}
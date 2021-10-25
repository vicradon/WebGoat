pipeline {
  agent any
  environment {
    SEMGREP_RULES = "p/security-audit p/secrets"
  }
  stages {
    stage('scan') {
      steps {
        sh 'env | sort'
        sh "docker run -v ${WORKSPACE}:/src --workdir /srcreturntocorp/semgrep-agent:v1 semgrep-agent --config p/security-audit --config p/secrets"
      }
    }
  }
}
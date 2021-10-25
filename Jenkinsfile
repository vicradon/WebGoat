pipeline {
  agent {
    docker { 
      image 'returntocorp/semgrep-agent:v1'
      args '-v $(pwd):/src'
    }
  }
  environment {
    SEMGREP_RULES = "p/security-audit p/secrets"
  }
  stages {
    stage('scan') {
      steps {
        sh 'semgrep-agent'
      }
    }
  }
}
pipeline {
  agent any
  stages {
    stage('Checkout SCM') {
      steps {
        git '/home/JenkinsDependencyCheck'
      }
    }

    stage('OWASP DependencyCheck') {
      steps {
        dependencyCheck(additionalArguments: '--format HTML --formatl XML')
      }
    }

  }
}
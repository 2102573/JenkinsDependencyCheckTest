pipeline {
 agent any
 stages {
  stage('Checkout SCM') {
   steps {
    git 'https://github.com/2102573/JenkinsDependencyCheckTest'
   }
  }

  stage('OWASP DependencyCheck') {
   steps {
    dependencyCheck additionalArguments: '--format HTML --format XML', odcInstallation: 'Default'
   }
  }
 } 
 post {
  success {
   dependencyCheckPublisher pattern: 'dependency-check-report.xml'
  }
 }
}

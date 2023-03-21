pipeline {
  agent any
  stages {
    stage('SCM') {
      steps {
        git(url: 'https://github.com/kHVreddy/maven-standalone-application.git', branch: 'master', credentialsId: 'git_credentials')
      }
    }

    stage('BUILD') {
      steps {
        sh '/usr/share/maven/bin/mvn clean package'
      }
    }

    stage('QA') {
      steps {
        withSonarQubeEnv(installationName: 'sonar', credentialsId: 'sonar-token', envOnly: true) {
          sh '/usr/share/maven/bin/mvn sonar:sonar'
        }

      }
    }

  }
}
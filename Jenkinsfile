pipeline {
  agent none
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

  }
}
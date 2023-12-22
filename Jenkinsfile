pipeline {
          stages {
                    stage('SonarQube') {
                              agent { label '!windows'}
                              steps {
                                        script { scannerHome = tool 'SonarQube Scanner' }
                                        withSonarQubeEnv('Sonarqubetest') {
                                                  sh "${scannerHome}/bin/sonar-scanner -Dsonar.projectKey=a-small-test"
                                        }
                              }
                    }
        stage('build') {
              agent { docker { image 'php:8.3.0-alpine3.19' } }
            steps {
                sh 'php --version'
            }
        }
    }
}

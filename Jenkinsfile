pipeline {
          agent { label '!windows'}
          stages('SonarQube') {
                    steps {
                              script { scannerHome = tool 'SonarQube Scanner' }
                              withSonarQubeEnv('Sonarqubetest') {
                                        sh "${scannerHome}/bin/sonar-scanner -Dsonar.projectKey=a-small-test"
                              }
                    }
          }
}

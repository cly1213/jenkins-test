pipeline {
    agent {
        docker { image "${params.buildNode}"
                  args '-u root:root -v $HOME/workspace/myproject:/myproject'
        }
    }
    stages {
       stage('Checkout SCM') {
          steps {
            checkout([
              $class: 'GitSCM',
              branches: [[name: "**" ]],
              userRemoteConfigs: [[
                url: 'https://github.com/cly1213/jenkins-test.git',
                credentialsId: '',
              ]]
             ])
           }
        }
        stage('Test') {
            steps {
                sh '''
                echo "test-again"
                '''
            }
        }
    }
}

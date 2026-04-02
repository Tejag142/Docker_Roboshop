pipeline {
    agent any
    
    environment{
        ksdjfn="kjshdhfi"

    }
    options{
        timeout(time: 30, unit: 'MINUTES')
        disableConcurrentBuilds()
    }
    parameters{
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: '', defaultValue: '', description: 'Enter the name of the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'toggle this value')
        choice(name: 'CHOICE', choices: ['one', 'two', 'three'], description: 'pick one')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter the Passsword')
        string(name: 'VERSION', defaultValue: '1.0.0', description: 'Enter version')
    }

    stages {
        stage ( 'Build' ) {
            steps {
                dir ('payment') {
 
                    sh """

                    docker build -t payment:${params.VERSION} .

                    echo 'Hello ${params.PERSON} Image is building '

                    """
                }
                
            }
        }
        stage ( 'Test' ) {
            steps {
                echo 'Testing done'
            }
        }
        stage ( 'Deploy' ) {
            steps {
                echo 'Deploy done'
            }
        }
    }
    post {
        always {
            echo 'I will always say Hello again!'
        }
        success {
            echo 'HelloSuccess'
        }
        failure {
            echo 'Hello Failure'
        }
    }
}
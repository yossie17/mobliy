pipeline {
    agent any 
    parameters {
        string(name: 'TEST_PARM', defaultValue: 'True', description: 'some test param')
        choice(name: 'TEST_CHOICE', choices: ['1', '2', '3'], description: 'some choice param')
        booleanParam(name: 'TEST_BOOL_PARM', defaultValue: 'True', description: 'some test boolean param' )
    }
    
    stages {
        stage('Build') { 
            steps {
                sh 'echo Building' 
            }
        }
        stage('Test') {
            when{
                expression{
                    params.TEST_BOOL_PARM
                }
            } 
            steps {
                sh 'echo Testing' 
            }
        }
        stage('Deploy') { 
            steps {
                sh 'echo Deploing' 
                sh 'echo ${TEST_CHOICE}' 
            }
        }
    }
}


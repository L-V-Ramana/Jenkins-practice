// pipeline {
//     agent any

//     stages {
//         stage('Build') {
//             steps {
//                 echo 'Building..'
//             }
//         }
//         stage('Test') {
//             steps {
//                 echo 'Testing..'
//             }
//         }
//         stage('Deploy') {
//             steps {
//                 echo 'Deploying....'
//             }
//         }
//     }
// }

pipeline {
    agent  { label 'agent-1' }
     options {
        timeout(time: 10, unit: 'SECONDS') 
        disableConcurrentBuilds()
    }
    environment { 
        course = 'jenkins'
    }
    stages {
        stage('Build') {
            steps {
                script{
                   sh  """
                        echo "Building.. in script"
                    """
                }
                
            }
        }
        stage('Test') {
            steps {
                echo "Testing.."
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploying...."
            }
        }
    }
    post { 
        always { 
            echo 'I will always say Hello again!'
            deleteDir()
        }
        changed { 
            echo ' changed Hello again!'
        }
        failure { 
            echo 'I will always say Hello on failure!'
        }
    }
}
// pipeline {
//     agent any 
//     stages {
//         stage('Build') { 
//             steps {
//                 sh 'python -m py_compile sources/add2vals.py sources/calc.py' 
//                 stash(name: 'compiled-results', includes: 'sources/*.py*') 
//             }
//         }
//         stage('Test') {
//             steps {
//                 sh 'py.test --junit-xml test-reports/results.xml sources/test_calc.py'
//             }
//             post {
//                 always {
//                     junit 'test-reports/results.xml'
//                 }
//             }
//         }
//         stage('Deliver') {
//                     steps {
//                         sh "pyinstaller --onefile sources/add2vals.py"
//                     }
//                     post {
//                         success {
//                             archiveArtifacts 'dist/add2vals'
//                         }
//                     }
//         }
//     }
// }

// pipeline {
//     agent any
//     environment {
//         // Using returnStdout
//         CC = """${sh(
//                 returnStdout: true,
//                 script: 'echo "clang"'
//             )}"""
//         // Using returnStatus
//         EXIT_STATUS = """${sh(
//                 returnStatus: true,
//                 script: 'exit 1'
//             )}"""
//     }
//     stages {
//         stage('Example') {
//             environment {
//                 DEBUG_FLAGS = '-g'
//             }
//             steps {
//                 sh 'printenv'
//             }
//         }
//     }
// }


pipeline {
    agent any
    environment {
        AWS_ACCESS_KEY_ID     = credentials('jenkins-aws-secret-key-id')
        AWS_SECRET_ACCESS_KEY = credentials('jenkins-aws-secret-access-key')
    }
    stages {
        stage('Example stage 1') {
            steps {
                 echo "$env.AWS_ACCESS_KEY_ID"
            }
        }
        stage('Example stage 2') {
            steps {
                 echo "$env.AWS_SECRET_ACCESS_KEY"
                // 
            }
        }
    }
}
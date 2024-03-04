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

pipeline {
    agent any
    environment {
        // Using returnStdout
        CC = """${sh(
                returnStdout: true,
                script: 'echo "clang"'
            )}"""
        // Using returnStatus
        EXIT_STATUS = """${sh(
                returnStatus: true,
                script: 'exit 1'
            )}"""
    }
    stages {
        stage('Example') {
            environment {
                DEBUG_FLAGS = '-g'
            }
            steps {
                sh 'printenv'
            }
        }
    }
}
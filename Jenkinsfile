node {
    stage('Version Check'){
           echo("---starting jenkins demo build process");
    bat 'node --version' 
    checkout([$class: 'GitSCM', branches: [[name: '*/master']],userRemoteConfigs: [[url: 'https://github.com/santoshkothapalli/java-demo.git']]])
    bat "mvn clean verify"
    }
    stage('Checkstyle') {
                    steps {
                        bat "mvn checkstyle:check"
                        recordIssues(tools: [checkStyle(reportEncoding: 'UTF-8')])
                    }
                }
    
    echo("--checkout successful")

}

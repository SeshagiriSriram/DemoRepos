#!groovy

pipeline {
    environment {
        JAVA_TOOL_OPTIONS = "-Duser.home=/tmp/maven"
        DEMO="Demo"
    }
   agent  any 
   //{  
      // docker {
         // image "ssriram12/maven-3.9.9:jdk13"
          //label "docker"
           //args "-v /tmp/maven:/tmp/maven -e MAVEN_CONFIG=/tmp/maven"
        //}
		//} 
 //any 
    

    stages {
        stage("Build") {
            steps {
                sh "mvn -version"
                sh "echo id = `id`"
		  //sh "sudo chown -R jenkins:jenkins /home/jenkins"
		// sh "echo TOKEN : $TOKEN" 
                sh "mvn clean compile"
            }
        }
	stage("Test") {
            steps {
                sh "mvn test"
            }
        }
	//stage("SonarAnalysis")
	//{
		//def scannerHome = tool 'SonarQubeScanner';
		// agent { label "docker" } 
		//steps {
			//sh "echo to be implemented" 
			//withSonarQubeEnv("SonarServer") {
			//sh "/home/sidkalpop/scanner/bin/sonar-scanner"
			//sh "echo to be implemented"
			//} 
		//}
	//} 

	stage("Package & Deploy") {
            steps {
                sh "mvn package install"
            }
        }

stage("Build Docker file") {
            steps {
                echo "Yet to be implemented" 
            }
        }

    }

    post {
        always {
            cleanWs()
        }
    }
}

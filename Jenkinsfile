node {
    stage('Checkout') {
		checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '53b3fd49-cacc-4960-baee-2e73e5f7d4dd', url: 'git@github.com:hiteshks2000/Testing.git']]])

}
    dir('my-app/')
    {
	    stage ('Compile and Archive')
	    {
		    bat 'mvn clean compile package'
	    }

	    stage ('Sonarqube')
	    {
		    bat 'mvn sonar:sonar'
	    }
    }
}

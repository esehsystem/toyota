// Powered by Infostretch 

timestamps {

node () {

	stage ('toyota stage - Checkout') {
 	 checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'gitHubCredential', url: 'https://github.com/esehsystem/toyota']]]) 
	}
	stage ('toyota stage - Build') {
 	
// Unable to convert a build step referring to "hudson.plugins.timestamper.TimestamperBuildWrapper". Please verify and convert manually if required.		// Maven build step
	withMaven(maven: 'maven 3.8.6') { 
 			if(isUnix()) {
 				sh "mvn install " 
			} else { 
 				bat "mvn install " 
			} 
 		}		// Maven build step
	withMaven(maven: 'maven 3.8.6') { 
 			if(isUnix()) {
 				sh "mvn sonar:sonar " 
			} else { 
 				bat "mvn sonar:sonar " 
			} 
 		}		// Maven build step
	withMaven(maven: 'maven 3.8.6') { 
 			if(isUnix()) {
 				sh "mvn deploy " 
			} else { 
 				bat "mvn deploy " 
			} 
 		} 
	}
}
}
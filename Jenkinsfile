pipeline {
    agent any
    // environment {
    //     FOLDER = terraformCommons.getFolderAndEnvironmentByProjectName()
    // }
	//def dir_list = []

stages {
	stage ('Clean WS'){
		steps {
		cleanWs()
		}
	}
	stage ('SCM'){
		steps {
			checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [[$class: 'RelativeTargetDirectory', relativeTargetDir: 'repo']], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/guannais/test-jenkins-file.git']]])
		}
	}
    stage('Retrive tf dirs:') {
		steps {
			// def ver_script = $/eval "'find . -iname \'*.tf\' -not -path \'*/\\.*\' | sed \'s/\\(.*\\)\\/.*/\\1/\' | grep -v \'^.$\' | sort | uniq'"/$
			// echo "${ver_script}"
			dirs = sh(script: "'find . -iname \'*.tf\' -not -path \'*/\\.*\' | sed \'s/\\(.*\\)\\/.*/\\1/\' | grep -v \'^.$\' | sort | uniq'", returnStdout: true)
			dirs_list = dirs.split('\n')
		}
	}
	// stage ('Print tf dirs:') {
	// 	dirs_list.each { item ->
    //     	echo "Hello ${item}"
    // 	}
	// }
	}
}
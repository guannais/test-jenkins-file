pipeline {
    agent any
    // environment {
    //      def dir_list = []
    // }
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
				script {
					ver_script = $/eval "find . -iname '*.tf' -not -path '*/\.*' | sed 's/\(.*\)\/.*/\1/' | grep -v '^.$' | sort | uniq"/$
					def dirs = sh(script: "${ver_script}", returnStdout: true)
					dirs_list = dirs.split('\n')
					echo "${dirs_list}"
				}
			}
		}
		stage ('Print tf dirs:') {
			steps {
				script {
					dirs_list.each { item ->
						echo "Hello ${item}"
					}
				}
			}
		}
	}
}


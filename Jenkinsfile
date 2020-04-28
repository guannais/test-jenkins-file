node() {
	stage ('Clean WS'){
		cleanWs()
	}
	stage ('SCM'){
		checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [[$class: 'RelativeTargetDirectory', relativeTargetDir: 'repo']], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/guannais/test-jenkins-file.git']]])
	}
    stage('Test 1:') {
		def ver_script = $/eval "find ./repo -iname '*.tf' -not -path '*/\.*' | sed 's/\(.*\)\/.*/\1/' | grep -v '^.$' | sort | uniq"/$
		echo "${ver_script}"
		dirs = sh(script: "${ver_script}", returnStdout: true)
		def dirs_list = dirs.split('\n')
		dirs.each { item ->
        	echo "Hello ${item}"
    	}
		// echo "${values}"
		// echo "${values[0]}"
		// echo "${values[1]}"

	}
}
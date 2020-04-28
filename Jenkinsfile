node() {
	stage ('SCM'){
		checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [[$class: 'RelativeTargetDirectory', relativeTargetDir: 'repo']], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/guannais/test-jenkins-file.git']]])
	}
    stage('Test 1:') {
		def ver_script = $/eval "find ./repo -iname "*.tf" -not -path '*/\.*' | sed 's/\(.*\)\/.*/\1/' | grep -v "^.$" | sort | uniq"/$
		echo "${ver_script}"
		POM_VERSION = sh(script: "${ver_script}", returnStdout: true)
		println POM_VERSION.split('\n')
		echo "${POM_VERSION}"
	}
}
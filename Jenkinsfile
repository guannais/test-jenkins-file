node() {
    stage('Test 1:') {

	def ver_script = $/eval "find . -iname "*.tf" -not -path '*/\.*' | sed 's/\(.*\)\/.*/\1/' | grep -v "^.$" | sort | uniq"/$
    echo "${ver_script}"
    POM_VERSION = sh(script: "${ver_script}", returnStdout: true)
    echo "${POM_VERSION}"
}

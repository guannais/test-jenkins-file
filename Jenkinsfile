node() {
    stage('Test 1:') {

	def ret = sh(script: 'find . -iname "*.tf" -not -path \'*/\\.*\' | sed \'s/\\(.*\\)\\/.*/\\1/\' | grep -v "^.$" | sort | uniq')
	print ret
	// ret.trim().tokenize('\r\n').each {
	// 	echo "File: "+it
	// }

    }
}

node() {
    stage('Test 1:') {

	def ret=SH(script: sh label: '', script: 'find . -iname "*.tf" -not -path \'*/\\.*\' | sed \'s/\\(.*\\)\\/.*/\\1/\' | grep -v "^.$" | sort | uniq')
	ret.trim().tokenize('\r\n').each {
		echo "File: "+it
	}

    }
}

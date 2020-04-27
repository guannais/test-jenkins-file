node() {
    stage('Test 1:') {
		def tmpDirPath = "./repo/"


		def tmpDir = new File(tmpDirPath)

def ret=bat(script: 'dir /s /b /a:D "'+tmpDir.absolutePath+'" 2>nul')
ret.trim().tokenize('\r\n').each {
	echo "File: "+it
}

    }
}

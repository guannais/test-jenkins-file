node() {
    stage('Test 1:') {
		def tmpDirPath = "./"
		def tmpDir = new File(tmpDirPath)

		// Output what eachDirRecurse does
		tmpDir.eachDirRecurse() { dir ->
			echo "Dir: ${dir}"
		}
    }
}

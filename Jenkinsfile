stage('all') {
    node('windock') {
        checkout scm
        withEnv(["MVN=${tool('mvn')}"]) {
            bat($/
                docker run --rm -v %MVN%:c:\mvn -v %CD%:c:\ws openjdk:8-windowsservercore-1809 cmd /c \mvn\bin\mvn -f \ws clean verify
            /$)
        }
    }
}

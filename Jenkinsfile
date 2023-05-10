@Library('jenkins-library') _

pipeline {
    agent any
    stages {
        stage ('Firts Job') {
            steps {
                script{
                    echo "Primer Trabajo"
                    //echo "La URL del repositorio es: ${hudson.plugins.git.UserRemoteConfig getUrl}"
                    //echo "La URL del repositorio es: ${scm.getLocations()[0].getURL()}"
                    def gitTool = tool 'git'
                    def git = gitTool.getGit()
                    def gitUrl = git.lsRemote("--get-url", "origin").trim()
                    println(gitUrl)
                }
            }
        }
    }
}
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
                    // def gitTool = tool 'git'
                    // def git = gitTool.getGit()
                    // def gitUrl = git.lsRemote("--get-url", "origin").trim()
                    GIT_REPO_URL = null
                    command = "grep -oP '(?<=url>)[^<]+' /var/lib/jenkins/jobs/${JOB_NAME}/config.xml"
                    GIT_REPO_URL = sh(returnStdout: true, script: command).trim();
                    echo "Detected Git Repo URL: ${GIT_REPO_URL}" 
                    //println(scm.userRemoteConfigs[0].url)
                }
            }
        }
    }
}
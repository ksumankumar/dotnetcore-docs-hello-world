pipeline {
    agent { label 'JDK-11' }
    stages {
        stage('git clone') {
            steps {
                git url: "https://github.com/ksumankumar/dotnetcore-docs-hello-world.git",
                    branch: "master"
            }
        }
        stage('build') {
            steps {
                sh "dotnet build dotnetcoresample.csproj"
                sh "dotnet publish dotnetcoresample.csproj"
            }
        }
        stage('archive artifats') {
            steps {
                archiveArtifacts artifacts: "**/*.dll"
            }
        }
    }
}
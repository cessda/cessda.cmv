pipeline {
    options {
        buildDiscarder logRotator(artifactNumToKeepStr: '5', numToKeepStr: '10')
    }

    environment {
        product_name = 'cmv'
	}

	agent {
        label 'jnlp-himem'
    }

	stages {
        stage('Pull SDK Docker Image') {
            agent {
                docker {
                    image 'openjdk:8'
                    reuseNode true
                }
            }
            // Building on master
            stages {
                stage('Build Project') {
                    steps {
                        withMaven {
                            sh './mvnw clean site'
                        }
                    }
                    when { branch 'main' }
                }
                // Not running on master - test only (for PRs and integration branches)
                stage('Test Project') {
                    steps {
                        withMaven {
                            sh './mvnw clean test'
                        }
                    }
                    when { not { branch 'main' } }
                }
                stage('Record Issues') {
                    steps {
                        recordIssues(tools: [java()])
                    }
                }
                stage('Run Sonar Scan') {
                    steps {
                        withSonarQubeEnv('cessda-sonar') {
                            withMaven {
                                sh './mvnw sonar:sonar'
                            }
                        }
                        timeout(time: 1, unit: 'HOURS') {
                            waitForQualityGate abortPipeline: true
                        }
                    }
                    when { branch 'main' }
                }
                stage('Deploy Project') {
                    steps {
                        withMaven {
                            sh './mvnw site package deploy:deploy'
                        }
                    }
                    when { branch 'main' }
                }
            }
        }
        stage("Run Downstream Jobs") {
            steps {
                build job: 'cessda.cmv.server/main', wait: false
            }
            when { branch 'main' }
        }
    }
}

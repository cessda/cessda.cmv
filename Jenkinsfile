pipeline {
    options {
        buildDiscarder logRotator(artifactNumToKeepStr: '5', numToKeepStr: '10')
    }

    environment {
        product_name = "cmv"
	}

	agent {
        docker {
            image 'maven:3-jdk-8'
        }
    }

	stages {
		// Building on master
		stage('Build Project') {
			steps {
				withMaven {
					sh "$MVN_CMD clean site"
				}
			}
			when { branch 'master' }
		}
        // Not running on master - test only (for PRs and integration branches)
		stage('Test Project') {
			steps {
                withMaven {
                    sh "$MVN_CMD clean test"
				}
			}
            when { not { branch 'master' } }
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
                        sh "$MVN_CMD sonar:sonar"
                    }
                }
            }
            when { branch 'master' }
        }
        stage("Get Sonar Quality Gate") {
            steps {
                timeout(time: 1, unit: 'HOURS') {
                    waitForQualityGate abortPipeline: false
                }
            }
            when { branch 'master' }
        }
		stage('Deploy Project') {
			steps {
				withMaven {
					sh "$MVN_CMD site package deploy:deploy"
				}
			}
			when { branch 'master' }
		}
        stage("Run Downstream Jobs") {
            steps {
                build job: 'cessda.cmv.server/master', wait: false
            }
            when { branch 'master' }
        }
	}
}
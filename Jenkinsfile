pipeline {
	agent any

	stages {
			stage('Checkout git repo') {
						steps {
						  git branch: 'master', url: 'https://github.com/AmitBansal73/devop_tutorial.git'
						  }
						}
			stage('Build') {
						steps {
						echo 'Hi this is Amit, running build'
						}
					}
			stage('build and publish') {
						steps {
										sh(script: "dotnet publish HelloAPI.sln -c Release ", returnStdout: true)
							}
					}
			stage('Test') {
						steps {
						input('Hi, Should we proceed?')
						echo 'proceeding'
						}
			}
			stage('QA') {
						when {
								not {
								branch 'master'
								}
						}
						steps {
							echo 'Hello'
						}
			}
			stage('Deploy') {
						parallel {
							stage ('Unit Test') {
												steps {
													echo 'Running the unit test'
												}
							}
							stage ('Integration Test') {
												steps{
												echo 'Running the unit test'
												}
							}
						}
			}
	}
}
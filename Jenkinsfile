pipeline {
	agent any

	stages {
			stage('Build') {
						steps {
						echo 'Hi this is Amit, running build'
						}
			}
			stage('Test') {
						steps {
						input('Hi, Should we proceed?')
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
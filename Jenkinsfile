node {
	def app

	stage('Clone repository') {
        /* Let's make sure we have the repository cloned to our workspace */

        checkout scm
    }

    stage('Build image') {
	/* Install docker */
	sh 'brew install docker'

        /* This builds the actual image; synonymous to
         * docker build on the command line */

        app = docker.build("MaroonBeret/NodeGoat-CI_CD-Test")
    }

    stage('Test image') {
        /* Ideally, we would run a test framework against our image.
         * For this example, we're using a simple message to indicate that the pipeline runs */

        app.inside {
            sh 'echo "This is a test message, after implementation and successful completion of tests, it should state: Tests passed"'
        }
    } 

}
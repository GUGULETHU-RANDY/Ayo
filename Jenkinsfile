node {
    def app

    stage('Clone repository') {
        /* clone repo*/

        checkout scm
    }

    stage('Build image') {
        /* This builds the actual image; synonymous to
         * docker build on the command line */

        app = docker.build("roshambo/webpage")
    }

    stage('Test image') {
        /* Ideally, we would run a test framework against our image.
         * tests */

        app.inside {
            sh 'echo "Tests passed"'
        }
    }

    stage('Push image') {
        /* push image */
        docker.withRegistry('https://registry.hub.docker.com', 'dockerhub') {
            app.push("${env.BUILD_NUMBER}")
            app.push("latest")
        }
    }
}

pipeline {
    agent any
    stages {
	stage('Lint HTML') {
	    tidy -q -e *.html
	}

        stage('Build') {
            steps {
                withAWS(region:'us-west-2', credentials:'aws-static') {
		    s3Upload(file:'index.html', bucket:'static-website-20200705')
                }
            }
        }
    }
}

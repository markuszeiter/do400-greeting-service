pipeline{
    agent{
        label "nodejs"
    }
    stages{
        stage("Install dependencies"){
            steps{
                sh "npm ci"
            }
        }

        stage("Check Style"){
            steps{
                sh "npm run lint"
            }
        }

        stage("Test"){
            steps{
                sh "npm test"
            }
        }

stage('Deploy') {
    steps {
sh '''
oc project rucdyw-greetings
oc start-build greeting-services --follow --wait
''' }
}

    }
}

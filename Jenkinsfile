node {
    try {
        stage ('Build') {
            sh "npm run deploy"
            slackSend color: 'good', message: "Build ${env.JOB_NAME} ${env.BRANCH_NAME} ${env.BUILD_NUMBER} (<${env.BUILD_URL}|Open>) terminé avec succès"
        }

    } catch(e) {
        slackSend color: 'danger', message: "Erreur ${env.JOB_NAME} ${env.BRANCH_NAME} ${env.BUILD_NUMBER} (<${env.BUILD_URL}|Open>) ${e.getMessage()}"
    }
  
}
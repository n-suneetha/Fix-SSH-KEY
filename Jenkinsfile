pipeline {
    agent any

    stages {
        stage('Multibranch-bitbucket-Conur-Credentials') {
            steps {
                script{
                    varVal =null
                //withCredentials([conjurSecretCredential(credentialsId: 'folder-3-regression-credential2', variable: 'CONJUR_SECRET')]) {
                     withCredentials([conjurSecretCredential(credentialsId: 'standalone-pipeline-regression-credential1', variable: 'CONJUR_SECRET')]) {
                   // withCredentials([conjurSecretCredential(credentialsId: 'no-folder-bitbucket-credential1', variable: 'CONJUR_SECRET')]) {
                  

                        varVal = CONJUR_SECRET
                     //sh 'echo Folder-1-Conjur Bitbucket Conjur Cred Cred Val '
                    }
                echo "Folder-1-Conjur Bitbucket Conjur Cred Cred Val  : ${varVal}"
                }
            }
        }
      
         stage('Multibranch-Git-Conur-Secret-Username-Credentials') {
            steps {
                script{
                    varVal =null
                  withCredentials([conjurSecretUsername(credentialsId: 'IDDDDD-STANDALONE-USERNAME', passwordVariable: 'CONJUR_SECRET', usernameVariable: 'USERNAME')]) {
                                       //  withCredentials([conjurSecretUsername(credentialsId: 'standalone-username-conjur-secret-username-IDO', passwordVariable: 'CONJUR_SECRET', usernameVariable: 'USERNAME')]) {
                        
                        varVal = CONJUR_SECRET
                    }
                echo "Folder-1-Conjur Bitbucket Conjur Secret Username Cred Val  : ${varVal}"
                }
            }
        }
      
    }
}

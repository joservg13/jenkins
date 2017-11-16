node {
stage('Deploy staging') {
echo 'Hello World'
}
stage ('Ask for input') {
input "Continue?"
}
stage('Deploy to production') {
echo 'Deploy to production'
}
  
  post {
    failure {
      mail to: 'joservg@meta4.com',
      subject: "Failed Pipeline: ${currentBuild.fullDisplayName}",
      body: "Something is wrong with ${env.BUILD_URL}"
    }
    success {
      echo 'Deploy to production'"${currentBuild.durationString}"
   }
}

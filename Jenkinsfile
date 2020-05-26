pipeline {

  // env.NODEJS_HOME = "${tool 'NodeJsv12.0.0'}"
  // env.PATH="${env.NODEJS_HOME}/bin:${env.PATH}"

  agent any
  stages{
    stage('Build') {
      steps {
        sh 'ant'
      }
    }
    stage('Docker Build') {
      steps {
       sh 'docker-compose build'
       }
     }
     stage('Docker Push'){
       steps{
     	  withDockerRegistry([ credentialsId: "dockerhub", url: "" ]){
     	   sh 'docker push saisriharsha333/php_img'
         sh 'docker push saisriharsha333/mysql'
 	     }
     }
   }
   stage('Deploy - Rundeck') {
      agent any
      steps {
        script {
          step([$class: "RundeckNotifier",
          rundeckInstance: "Rundeck",
          options: """
            BUILD_VERSION=$BUILD_NUMBER
          """,
          jobId: "f9927e54-5d40-4e3a-a773-58b51c7a7e91"])
        }
      }
    }
	stage('Test') {
      steps {
        sh 'PATH=/home/sriharsha/Desktop/8th_sem/SPE/project:$PATH selenium-side-runner Test1.side Test2.side -c "browserName=chrome goog:chromeOptions.args=[headless]" --output-directory=results --output-format=junit'

        // sh 'PATH=/home/manideep/Desktop/Online-Notes-Sharing:$PATH selenium-side-runner Test1.side Test2.side -c "browserName=chrome goog:chromeOptions.args=[headless]" --output-directory=results --output-format=junit'
        // sh 'node -v'
        // sh 'selenium-side-runner Test1.side Test2.side -c "browserName=chrome goog:chromeOptions.args=[headless]" --output-directory=results --output-format=junit'
      }
    }
  }
}

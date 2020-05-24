pipeline {
  agent any
  stages{
<<<<<<< HEAD
    stage('Build') {
      steps {
        sh 'ant'
      }
    }
	stage('Test') {
      steps {
        // sh 'PATH=/home/sriharsha/Desktop/8th_sem/SPE/project:$PATH selenium-side-runner Test1.side Test2.side -c "browserName=chrome goog:chromeOptions.args=[headless]" --output-directory=results --output-format=junit'
        // sh 'PATH=/home/manideep/Desktop/Online-Notes-Sharing:$PATH selenium-side-runner Test1.side Test2.side -c "browserName=chrome goog:chromeOptions.args=[headless]" --output-directory=results --output-format=junit'
        sh 'selenium-side-runner Test1.side Test2.side -c "browserName=chrome goog:chromeOptions.args=[headless]" --output-directory=results --output-format=junit'
      }
=======
  //   //stage('Build') {
  //     //steps {
  //       //sh 'ant'
  //     //}
  //   //}
	// //stage('Test') {
  //     //steps {
  //       //PATH=/home/sriharsha/Desktop/8th_sem/SPE/project:$PATH selenium-side-runner Test1.side Test2.side -c "browserName=chrome goog:chromeOptions.args=[headless]" --output-directory=results --output-format=junit
  //     //}
  //   //}
  //   pipeline {
  //   agent { dockerfile true }
  //   stages {
  //       stage('Test') {
  //           steps {
  //               sh 'docker compose up'
  //           }
  //       }
>>>>>>> eca6185f753ee01a6a11c3f04626844c57c00699
    }
}
  }
}

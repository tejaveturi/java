pipeline{
  agent {
    lable 'master'
  }
  stages{
    stage("PRINT"){
      steps{
        sh 'echo $JOB_NAME'
    }
    }
    stage("WRITE"){
      steps{
        sh 'echo $BUILD_NUMBER >> build_number'
      }
    }
    stage("READ"){
      steps{

        sh 'cat build_number'
      }
    }
  }
  post{
    success{
      archiveArtifacts artifacats: 'build_number' , figureprint: true
    }
  }
}

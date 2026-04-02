pipeline{
  agent any
  stages{
    stage('Checkout'){
      steps{
        git url: 'https://github.com/MCA25092/Dockerwaala', branch: 'master'
      }
    }
    stage('Build Image'){
      steps{
        bat 'docker build -t mywebsite .'
      }
    }
    stage('Stop Old Containers'){
      steps{
        bat 'docker stop mycount || exit 0'
        bat 'docker rm mycount || exit 0'
      }
    }
    stage('Run Image'){
      steps{
        bat 'docker run -d -p 7000:80 --name mycount mywebsite'
      }
    }
  }
}

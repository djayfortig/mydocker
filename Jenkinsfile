pipeline{
  agent any 
  stages{
    stage('1. Checkout'){
      git 'https://github.com/djayfortig/mydocker.git'
    }
  }
  stage('2. Build Image'){
    steps{
      bat 'docker build -t myweb .'
    }
  }
  stage('3. Stop all Containers'){
    steps{
      bat 'docker stop mycount || exit 0'
      bat 'docker rm mycount || exit 0'
    }
  }
  stage('4. Run the Image- Containerize'){
    steps{
      bat 'docker run -d -p 8000:80 --name mycount myweb'
    }
  }
}

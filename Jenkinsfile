pipeline{
  agent any
  tools{
    maven 'Maven'
    jdk 'JDK21'
  }
  stages{
    stage('Checkout'){
      steps{
        git url : 'https://github.com/Manyaharish14/demo2.git',
          branch : 'master'
        credentials : 'github-token
      }
    }
    stage('Build'){
      steps{
        sh 'mvn clean compile'
      }
    }
    stage('Test'){
      steps{
        sh 'mvn test'
      }
    }
    stage('Package'){
      steps{
        sh 'mvn package'
      }
    }
  }
  post{
    success{
      email text(
        subject : 'SUCCESS: ${JOB_NAME} #${BUILD_NUMBER}',
        body : 'Bulid succeeded!\nCheck: ${BUILD_URL}',
        to : 'manyaharish142gmail.com'
      }
    }
    failure{
      email text(
        subject : 'SUCCESS: ${JOB_NAME} #${BUILD_NUMBER}',
        body : 'Bulid succeeded!\nCheck: ${BUILD_URL}',
        to : 'manyaharish142gmail.com'
      }
    }
        
}

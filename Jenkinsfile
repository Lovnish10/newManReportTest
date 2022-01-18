pipeline{
  
  agent any
  
  stages{

      stage('version checking'){
       steps{

           bat 'node --v'
           bat 'npm --v'
       }
      }

      stage('install'){
          steps{
              bat 'npm install'
              bat 'npm install newman'
              bat 'npm install newman-reporter-htmlextra'
          }
      }

      stage('genrate report'){
          steps{
          bat 'newman run newmanApiTest.json --disable-unicode -e test_env.json --r htmlextra'
          }
      }
  }

}

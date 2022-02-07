pipeline{
  
  agent any
  
  stages{
    
    
    

      stage('version checking'){
       steps{

           bat 'node --version'
           bat 'npm --version'
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
                     bat "newman run newmanApiTest.json --disable-unicode -e test_env.json --reporters=cli,htmlextra"
          }
      }

      stage('Upload to Aws S3'){
          steps{
              bat "echo 'printing uploading html to s3'"
          }
      }
  }

}

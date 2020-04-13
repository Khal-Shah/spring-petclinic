#!/usr/bin/env groovy

pipeline 
{ 
  agent any
  stages 
  { 
    stage('Build') 
    {
      steps 
      {
        sh './mvnw clean'
        slackSend channel: '#345slacknotification', 
                          color: '#ff0000'
                          message: 'Build successful'

      } 
    }

    stage('Test') 
    {
      steps 
      {
        sh './mvnw test'
        slackSend channel: '#345slacknotification', 
                          message: 'Test successful'
      } 
    }
    
    stage('Package') 
    {
      steps 
      {
        sh './mvnw package'
        slackSend channel: '#345slacknotification', 
                          message: 'Package successful'
      } 
    }
    
     stage('Deploy')
    {
      agent any
      when
      {
        branch 'master'
      }
      steps 
      {
        sh './mvnw deploy'
        slackSend channel: '#345slacknotification', 
                          message: 'Deploy successful'
      }
    }
  } 
  
}

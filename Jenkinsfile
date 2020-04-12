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
      } 
    }

    stage('Test') 
    {
      steps 
      {
        sh './mvnw test'
      } 
    }
    
    stage('Package') 
    {
      steps 
      {
        sh './mvnw package'
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
      }
    }
  } 
  post 
	{
     slackSend color: 'good', message: 'Message from Jenkins Pipeline: Build successful.'
 	}
}

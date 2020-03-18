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
      when 
      {
        not 
        {
           branch 'master'
        }
      }

      steps 
      {
        './mvnw deploy'
      }
    }
    
  } 
}

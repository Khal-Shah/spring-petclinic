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
    
    stage('Package') 
    {
      steps 
      {
        sh './mvnw package'
      } 
    }

  } 
}

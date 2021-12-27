pipeline { 
 environment { 
 registry = "sohaibber/tp4jenkinsfile" 
 registryCredential = 'dockerhub' 
 dockerImage = '' 
 } 
 agent any 
 stages { 
 stage('Cloning Git') { 
 steps { 
 git 'https://github.com/sohaibber/tp4_devops'  } 
 } 
 stage('Building image') { 
 steps{ 
 script { 
 dockerImage = docker.build registry + ":$BUILD_NUMBER"  } 
 } 
 } 
 stage('Publish Image') { 
 steps{ 
 script { 
 docker.withRegistry( '', registryCredential ) { 
 dockerImage.push() 
 } 
 } 
 } 
 } 
 } 
} 
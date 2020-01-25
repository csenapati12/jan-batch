node(){
    
    stage('cloning the code'){
      echo "Cloning"  
      checkout changelog: false, poll: false, scm: [$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '525445bb-7791-4e3a-97b0-955fba458575', url: 'https://github.com/csenapati12/maven-samples.git']]]
    }
     stage('compile'){
      sh label: '', script: 'mvn compile'
      echo "compile"  
    }
     stage('packaging'){
         sh label: '', script: 'mvn package'
      echo "packaging" 
    }
     stage('Sonar analysis'){
         sh label: '', script: 'mvn compile sonar:sonar'
      echo "Sonar analysis"  
    }
     stage('Dockerization'){
      echo "Dockerization"  
    }
    
}

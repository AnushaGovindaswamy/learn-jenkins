// pipeline {
//  agent {
//   node{
//    label 'workstation'
//      }
//  }
//  stages {
//
//    stage('one') {
//    steps {
//    sh 'echo hello anusha welcome'
//    }
//   }
//  }
//
//
// }

pipeline {
 agent {
  node {
   label 'workstation'
  }
  }
  triggers {
  pollscm('H/2 * * * *')
  }
  options {
  ansicolor('xterm')
  }
  environment
  {
     Sample_url= "www.google.com"

    }
  parameters
  {
    string(name:'PERSON', defaultvalue:'MR.JENKINS', description:'choose person')
  }

  stages {
  stage('one'){
   input {
    message "Do You approve"
    ok "Yes"

   }
   steps{
   sh 'echo ${Sample_url}'
   sh 'echo ${PERSON}'

   }
 }
 stage('Two'){
   when {
    expression{
     Git_Branch == "main"

  }
   }
   steps
   {
    sh 'echo stage two'
   }

 }
 stage('Three'){
    when {
     expression{
      Git_Branch == "origin"

   }
    }
    steps
    {
     sh 'echo stage three'
    }
    }
    post {
     always{
      sh 'clean up after activity'
     }
    }
}
}

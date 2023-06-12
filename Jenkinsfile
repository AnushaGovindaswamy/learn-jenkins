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

// pipeline {
//  agent {
//   node {
//    label 'workstation'
//   }
//   }
//   triggers {
//   pollscm('H/2 * * * *')
//   }
//   options {
//   ansicolor('xterm')
//   }
//   environment
//   {
//      Sample_url= "www.google.com"
//
//     }
//   parameters
//   {
//     string(name:'PERSON', defaultvalue:'MR.JENKINS', description:'choose person')
//   }
//
//   stages {
//   stage('one'){
//    input {
//     message "Do You approve"
//     ok "Yes"
//
//    }
//    steps{
//    sh 'echo ${Sample_url}'
//    sh 'echo ${PERSON}'
//
//    }
//  }
//  stage('Two'){
//    when {
//     expression{
//      Git_Branch == "main"
//
//   }
//    }
//    steps
//    {
//     sh 'echo stage two'
//    }
//
//  }
//  stage('Three'){
//     when {
//      expression{
//       Git_Branch == "origin"
//
//    }
//     }
//     steps
//     {
//      sh 'echo stage three'
//     }
//     }
//     post {
//      always{
//       sh 'clean up after activity'
//      }
//     }
// }
// }
pipeline {

 agent {
   node {
     label 'workstation'
   }
 }

 triggers { pollSCM('H/2 * * * *') }

 options {
   ansiColor('xterm')
 }

 parameters {
   string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
 }

 environment {
   SAMPLE_URL="example.com"
 }

 stages {

   stage('One') {
     input {
       message "Do you Approve?"
       ok "Yes"
     }
     steps {
       sh 'echo Hello World'
       sh 'echo Hello Universe'
       sh 'echo ${SAMPLE_URL}'
       sh 'echo PERSON - ${PERSON}'
     }
   }

   stage('Two') {
     when {
       expression {
         GIT_BRANCH == "origin/test"
       }
     }
     steps {
       sh 'env'
     }
   }

 }

 post {
   always {
     sh 'echo Post CleanUP steps'
   }
 }

}

pipeline {
  agent any
  stages {
    stage('Parallel') {
      parallel {

        stage('One') {
          steps {
            sh 'echo One'
          }
        }
        stage('Two') {
          steps {
            sh 'echo Two'
          }
        }
        stage('Three') {
          steps {
            sh 'echo Three'
          }
        }

      }
    }



  }
}


#!groovy
library identifier: 'Jenkins2@master', retriever: modernSCM(
        [$class: 'GitSCMSource' ,
         remote: 'https://github.com/DikshaTomar101/Jenkins'])
pipeline {
   agent any
    options{
       timestamps()
       ansiColor( 'xterm' )
   }
   stages {
      stage( 'Coloured Outputs with git commit id' ) {
         steps {
             script{
                 logs.info "SUCCESS"
                 logs.warn "WARNING"
                 def gitId=sh(script: 'git rev-parse HEAD' , returnStdout: true)
                 logs.gitCommitId(gitId)
             }
         }
      }
  }
}

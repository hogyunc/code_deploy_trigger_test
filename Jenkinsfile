node {
    docker.image('debian_build').inside("-u root") {
        sshagent(['hogyunc_git']){[docker-image].inside("--volume $SSH_AUTH_SOCK:$SSH_AUTH_SOCK [otherargs]"){
        
          stage 'Build'
          sh 'echo HELLO WORLD'
          stage 'DONE Good'

      }
    }
  }
}
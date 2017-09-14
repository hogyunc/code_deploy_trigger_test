thub-node {
    docker.image('debian_build').inside("-u root") {
        sshagent(['github-hogyunc']){[docker-image].inside("--volume $SSH_AUTH_SOCK:$SSH_AUTH_SOCK [otherargs]"){
        
          stage 'Build'
          sh 'echo HELLO WORLD'
          stage 'DONE Good'

      }
    }
  }
}

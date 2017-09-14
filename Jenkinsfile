node {

	withCredentials([[$class: 'UsernamePasswordMultiBinding', credentialsId: 'jumpcloud-hogyunc',
    usernameVariable: 'ARTIFACTORY_USER', passwordVariable: 'ARTIFACTORY_PASSWORD']]) {
    stage 'Testing Code'
	checkout scm
    sh 'git submodule update --init'
    }


    docker.image('debian_build').inside("-u root") {
        sshagent(['github-hogyunc']){[docker-image].inside("--volume $SSH_AUTH_SOCK:$SSH_AUTH_SOCK [otherargs]"){
        
          stage 'Build'
          sh 'echo HELLO WORLD'
          stage 'DONE Good'

      }
    }
  }
}

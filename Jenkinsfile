node {

	withCredentials([[$class: 'UsernamePasswordMultiBinding', credentialsId: 'jumpcloud-hogyunc',
    usernameVariable: 'ARTIFACTORY_USER', passwordVariable: 'ARTIFACTORY_PASSWORD']]) {
    stage 'Testing Code'
	checkout scm
    sh 'ls'
    }

    sshagent(['github-hogyunc']){
    docker.image('e1baf4c2be7a').inside("--volume $SSH_AUTH_SOCK:$SSH_AUTH_SOCK -u root") {
          sh 'ssh-add -l'
          stage 'Build'
          sh 'echo HELLO WORLD'
          stage 'DONE Good'

      
    }
  }
}

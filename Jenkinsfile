node {
  withCredentials([[$class: 'UsernamePasswordMultiBinding', credentialsId: 'hogyunc_git',
    usernameVariable: 'ARTIFACTORY_USER', passwordVariable: 'ARTIFACTORY_PASSWORD']]) {
    stage 'Testing Code'
        $class: 'GitSCM',
        branches: scm.branches,
        extensions: scm.extensions + [[
          $class: 'SubmoduleOption',
          parentCredentials: true,
          disableSubmodules: false,
          recursiveSubmodules: true,
          trackingSubmodules: false
        ]],
        userRemoteConfigs: scm.userRemoteConfigs
    ])
    }
    docker.image('debian_build').inside("-u root") {
        sshagent(['hogyunc_git']){[docker-image].inside("--volume $SSH_AUTH_SOCK:$SSH_AUTH_SOCK [otherargs]"){
        
          stage 'Build'
          sh 'echo HELLO WORLD'
          stage 'DONE Good'

      }
    }
  }
}
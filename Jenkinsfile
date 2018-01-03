stage 'Checking connectivity'

node {
    deleteDir()
    checkout scm
    
    wrap([$class: 'AnsiColorBuildWrapper', colorMapName: "xterm"]) {
        ansiblePlaybook(
            playbook: 'copy.yml',
            inventory: 'inventory',
            colorized: true)
    }
}
stage "Check syntax"

node {
    wrap([$class: 'AnsiColorBuildWrapper', colorMapName: "xterm"]) {
        ansiblePlaybook(
            playbook: 'copy.yml',
            inventory: 'inventory',
            extras: '--syntax-check',
            colorized: true
            )
    }
}

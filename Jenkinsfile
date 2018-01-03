
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
stage 'Checking dry run'

node {
    deleteDir()
    checkout scm
    
    wrap([$class: 'AnsiColorBuildWrapper', colorMapName: "xterm"]) {
        ansiblePlaybook(
            playbook: 'copy.yml',
            inventory: 'inventory',
            extras: '--check --diff',
            colorized: true)
    }
}

stage "verbose output"
node  {
    wrap([$class: 'AnsiColorBuildWrapper', colorMapName: "xterm"]) {
        ansiblePlaybook(
            playbook: 'copy.yml',
            inventory: 'inventory',
            extras: '-vvv',
            colorized: true
           )
    }
    
}



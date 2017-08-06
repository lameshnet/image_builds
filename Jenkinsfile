node('simplicify-ec2-ubuntu'){
        stage('Setup Env') {
            sh 'mkdir image_builds'
            dir('image_builds'){
                checkout scm
            }
            checkout([$class: 'GitSCM',
                branches: [[name: '*/master']],
                doGenerateSubmoduleConfigurations: false,
                extensions: [[$class: 'RelativeTargetDirectory',
                relativeTargetDir: 'meta-openembedded']],
                submoduleCfg: [],
                userRemoteConfigs: [[url: 'git://git.openembedded.org/meta-openembedded']]])
            checkout([$class: 'GitSCM',
                branches: [[name: '*/pyro']],
                doGenerateSubmoduleConfigurations: false,
                extensions: [[$class: 'RelativeTargetDirectory',
                relativeTargetDir: 'meta-openembedded']],
                submoduleCfg: [],
                userRemoteConfigs: [[url: 'git://git.yoctoproject.org/meta-raspberrypi.git']]])

            git branch: 'pyro', url: 'git://git.yoctoproject.org/poky.git'
            sh 'ls'
            sh 'source oe-init-build-env'
            sh 'cp ~/image_builds/conf/bblayers.conf conf/'
            sh 'bitbake'
        }
}

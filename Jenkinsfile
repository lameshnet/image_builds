node('simplicify-ec2-ubuntu'){
        stage('Setup Env') {
        checkout([$class: 'GitSCM',
        branches: [[name: '*/master']],
        doGenerateSubmoduleConfigurations: false,
        extensions: [[$class: 'RelativeTargetDirectory',
            relativeTargetDir: 'meta-openembedded']],
        submoduleCfg: [],
        userRemoteConfigs: [[url: 'git://git.openembedded.org/meta-openembedded']]])

            sh 'ls'
            git branch: 'pyro', url: 'git://git.yoctoproject.org/meta-raspberrypi.git'
            sh 'ls'
            git branch: 'pyro', url: 'git://git.yoctoproject.org/poky.git'
            sh 'ls'
            sh 'source poky/oe-init-build-env'
            sh 'cp ~/image_builds/conf/bblayers.conf conf/'
            sh 'bitbake'
        }
}

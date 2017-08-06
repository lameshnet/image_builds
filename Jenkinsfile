node('simplicify-ec2-ubuntu'){
        stage('Setup Env') {
            git url: 'git://git.openembedded.org/meta-openembedded'
            git branch: 'pyro', url: 'git://git.yoctoproject.org/meta-raspberrypi.git'
            git branch: 'pyro', url: 'git://git.yoctoproject.org/poky.git'
            sh 'mv meta-* poky'
            sh 'source poky/oe-init-build-env'
            sh 'cp ~/image_builds/conf/bblayers.conf conf/'
            sh 'bitbake'
        }
}

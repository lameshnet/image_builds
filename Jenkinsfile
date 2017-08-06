node('simplicify-ec2-ubuntu'){
        stage('Clone Source') {

            git: "git://git.openembedded.org/meta-openembedded"
            git branch: 'pyro', url: 'git://git.yoctoproject.org/meta-raspberrypi.git'
            git branch: 'pyro', url: 'git://git.yoctoproject.org/poky.git'
            
        }
}

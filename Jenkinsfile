node(){
    stage('Cloning Git') {
        checkout scm
    }
    stage('Install cli') {
        nodejs('nodejs') {
            sh 'npm i -g @angular/cli '
            echo "Modules installed"
        }

    }

    stage('Install dependencies') {
        nodejs('nodejs') {
            sh 'npm install'
            echo "Modules installed"
        }

    }
    stage('Build') {
        nodejs('nodejs') {
            sh 'ng build'
            echo "Build completed"
        }

    }
     stage('copy') {
        sh 'cp -a /home/ec2-user/jenkins/workspace/ngautomation/dist/fuse/. /var/www/html/'
    }

    // stage('Package Build') {
    //     sh "tar -zcvf bundle.tar.gz dist/automationdemo/"
    // }

    // stage('Artifacts Creation') {
    //     fingerprint 'bundle.tar.gz'
    //     archiveArtifacts 'bundle.tar.gz'
    //     echo "Artifacts created"
    // }

    // stage('Stash changes') {
    //     stash allowEmpty: true, includes: 'bundle.tar.gz', name: 'buildArtifacts'
    // }
}


// node('awsnode') {
//     echo 'Unstash'
//     unstash 'buildArtifacts'
//     echo 'Artifacts copied'

//     echo 'Copy'
//     sh "yes | sudo cp -R bundle.tar.gz /var/www/html && cd /var/www/html && sudo tar -xvf bundle.tar.gz"
//     echo 'Copy completed'
// }

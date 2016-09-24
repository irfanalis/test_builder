node('newnode') {
    stage 'CI'

    dir('gcloud') {
        git branch: 'master', url: 'ssh://gerrit.plumgrid.com:29418/gcloud'
        sh 'mkdir -p build; cd build; cmake ..; make install;'
    }

    sh 'aurora ls project'
    stage 'pipeline'
    sh "aurora ls build"
    stage 'cleanup'
    sh "aurora ls instances"
}

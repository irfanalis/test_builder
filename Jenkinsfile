node('newnode') {
    stage 'CI'

    dir('gcloud') {
        git branch: 'master', url: 'ssh://gerrit.plumgrid.com:29418/gcloud'
        sh 'mkdir -p build; cd build; cmake ..; make install;'
    }
    sh "export PATH=$PATH:/home/plumgrid/google-cloud-sdk/bin:${WORKSPACE}/gcloud/build/aurora:${WORKSPACE}/gcloud/build/aurora/pipeline_scripts/alps:${WORKSPACE}/gcloud/build/aurora/pipeline_scripts/;"
    sh 'aurora ls project'
    stage 'pipeline'
    sh "aurora ls build"
    stage 'cleanup'
    sh "aurora ls instances"
}

node('newnode') {
    stage 'CI'
    sh 'aurora ls project'
    stage 'pipeline'
    sh "aurora ls build"
    stage 'cleanup'
    sh "aurora ls instances"
}

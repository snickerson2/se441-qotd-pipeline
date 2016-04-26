node {
   stage "Checkout"
   git 'https://github.com/snickerson2/se441-qotd-pipeline.git'

   def gradleHome = tool 'Gradle 2.11'
   stage "Build"
   sh "${gradleHome/bin/gradle assemble uploadArchives"

   step([$class: 'ArtifactArchiver', artifacts: '**/*.war', fingerprint: true])
}


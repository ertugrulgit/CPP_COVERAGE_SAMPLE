pipeline {
    agent {label 'cfs-slave'}
    stages {
        stage('build') {
            steps {
                sh 'echo $GIT_COMMIT'
                sh 'echo $GIT_PREVIOUS_SUCCESSFUL_COMMIT'
//                 sh "git diff --name-only --oneline $GIT_PREVIOUS_SUCCESSFUL_COMMIT $GIT_COMMIT > result2.txt"
//                 sh "echo foo > result.txt"
                sh 'git diff --name-only --oneline $GIT_PREVIOUS_SUCCESSFUL_COMMIT $GIT_COMMIT > .\filelist.txt'
               sh '/home/vagrant/embold/wrapper/bin/embold-cl-cd-wrapper -c repository-configuration.json -lf filelist.txt'
             //   sh 'mvn clean install'
             //  sh '$CORONA_HOME/scanboxwrapper/bin/gammascanner -c ./repository-configuration.json -u http://10.1.100.13:3000/ -t eyJhbGciOiJFUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MTYyNjM3Nzc3NDE2MywiaWF0IjoxNjI2Mzc3Nzc0fQ.2I3TddqB4SJ49zmnfybN8an53L6Evvu2F6kRwuyzDNN4ZPzOwl_oWdkx-CxFa50STBZqqR5cjFtmopoq3UCQkA -r 3df600ffbcf10f6402d5f82af99883d7'
              // sh '/var/jenkins_home/embold_RepoLevel_QualityGate_and_Rating_Check.sh http://192.168.2.38:3001 5403557beb7fee031f6e795870b0132d eyJhbGciOiJFUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MTYyNjg3Nzc5OTU4NywiaWF0IjoxNjI2ODc3Nzk5fQ.-o4yorCUTl2DkL-f0qOMTKcEO4L_FJ33xQE1DJkGjdhBpRtzNfO9OwMs-4QBvulqRB6UiNCvlqYh-aFMsRRWew 5.0'
            }
        }
    }
}

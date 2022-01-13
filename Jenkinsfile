pipeline {
    agent {label 'cfs-slave'}
    stages {
        stage('build') {
            steps {
                sh 'echo $GIT_COMMIT'
                sh 'echo $GIT_PREVIOUS_SUCCESSFUL_COMMIT'
//                 sh "git diff --name-only --oneline $GIT_PREVIOUS_SUCCESSFUL_COMMIT $GIT_COMMIT > result2.txt"
//                 sh "echo foo > result.txt"
                sh '''
                [ "$GIT_COMMIT" != "$GIT_PREVIOUS_SUCCESSFUL_COMMIT" ] && git diff --name-only --oneline $GIT_PREVIOUS_SUCCESSFUL_COMMIT $GIT_COMMIT > filelist.txt || { echo no changes; rm -f filelist.txt; }
                [ -f filelist.txt ] && /home/vagrant/embold/wrapper/bin/embold-ci-cd-wrapper -c repository-configuration.json -lf filelist.txt 
                '''
                //sh 'git diff --name-only --oneline $GIT_PREVIOUS_SUCCESSFUL_COMMIT $GIT_COMMIT > filelist.txt'
               //sh '/home/vagrant/embold/wrapper/bin/embold-ci-cd-wrapper -c repository-configuration.json -lf filelist.txt'
             //   sh 'mvn clean install'
             //  sh '$CORONA_HOME/scanboxwrapper/bin/gammascanner -c ./repository-configuration.json -u http://10.1.100.13:3000/ -t eyJhbGciOiJFUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MTYyNjM3Nzc3NDE2MywiaWF0IjoxNjI2Mzc3Nzc0fQ.2I3TddqB4SJ49zmnfybN8an53L6Evvu2F6kRwuyzDNN4ZPzOwl_oWdkx-CxFa50STBZqqR5cjFtmopoq3UCQkA -r 3df600ffbcf10f6402d5f82af99883d7'
                sh '/home/vagrant/embold/emb-integration-samples/jenkins_quality_gate_checks/embold_RepoLevel_QualityGate_and_Rating_Check.sh http://10.1.100.13:3000 1757b653d313385ece089b70fa0ef907 eyJhbGciOiJFUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MTYyNjM3Nzc3NDE2MywiaWF0IjoxNjI2Mzc3Nzc0fQ.2I3TddqB4SJ49zmnfybN8an53L6Evvu2F6kRwuyzDNN4ZPzOwl_oWdkx-CxFa50STBZqqR5cjFtmopoq3UCQkA 5.0'
            }
        }
    }
}

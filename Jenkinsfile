pipeline {
    agent {
        label 'linux'
    }
    stages {
        stage('checkout role'){
            steps{
                dir('mnt-homeworks-ansible') {
                    git branch: 'main', credentialsId: '13c50aa8-dc9e-4c1f-96a2-956adf5a594c', url: 'git@github.com:cryptowebsite/mnt-homeworks-ansible.git'
                }
            }
        }
        stage('Install molecule') {
            steps{
                dir('mnt-homeworks-ansible'){
                    sh 'pip3 install -r test-requirements.txt'
                }
                sh "echo =============="
            }
        }
        stage('Run Molecule'){
            steps{
                dir('mnt-homeworks-ansible'){
                    sh 'molecule test'
                }
            }
        }
    }
}

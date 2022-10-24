pipeline {
    agent { label 'pythonproject' }
    stages {
        stage('vcs') {
            steps {
                git branch: 'master', url:'https://github.com/rohi3369/python-webcount.gitc'
            }

        }
        stage('build') {
            steps {
                sh '''pip3 install -r requirements.txt
                      tox'''
            }
        }

        stage('test reports') {
            steps {
                junit 'junit-py39.xml'
            }
        }
        stage('artifacts') {
            steps {
               archiveArtifacts artifacts: '**/webcount-0.1.zip'
            }
        }
    }
}            


/* sudo apt install python3.9 -y 
 python3.9 --version
 sudo apt install -y python3-pip
 python3 -m pip install --upgrade pip setuptools wheel
 =>  pip3 install -r requirements.txt
 pip install pytest
 pip install tox
 sudo apt install tox -y
 export PATH="/usr/lib/jenkins/.local/bin:$PATH"
 =>   tox
 */
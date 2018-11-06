pipeline {
    agent {
        label 'master'
    }
    environment {
     PLAYBOOK_PATH = "~/workspace/JenkinsFile_GIT_Repo/ansible/playbooks/flex"
   }
    parameters {
        choice(
            // choices are a string of newline separated values
            choices: '\rabbitmq\nredis\ntusker\npheme\ndroms\nopenadr2b\nceep\nndianoga\ncascade\nrtcc\nfam-backend\nall',
            description: '',
            name: 'REQUESTED_ACTION')
    }

    stages {
        stage ('demo-preview-rabbitmq') {
            when {
                // Only say hello if a "rabbitmq" is requested
                expression { params.REQUESTED_ACTION == 'rabbitmq'  || params.REQUESTED_ACTION == 'all'}
            }
            steps {
                echo 'Depoying demo-preview-rabbitmq'
                
                sh "cd ${PLAYBOOK_PATH} && cp ~/ansible.cfg ansible.cfg && sudo ansible-playbook -i ${PLAYBOOK_PATH}/inventory/demo-preview ${PLAYBOOK_PATH}/rabbitmq.yml --tags update --vault-password-file  ~/.agv"

            }
        }
        stage ('demo-preview-redis') {
            when {
                // Only say hello if a "redis" is requested
                expression { params.REQUESTED_ACTION == 'redis'  || params.REQUESTED_ACTION == 'all'}
            }
            steps {
                echo 'Depoying demo-preview-cascade'
                
                sh "cd ${PLAYBOOK_PATH} && cp ~/ansible.cfg ansible.cfg && sudo ansible-playbook -i ${PLAYBOOK_PATH}/inventory/demo-preview ${PLAYBOOK_PATH}/redis.yml --tags update --vault-password-file  ~/.agv"
                
            }
        }
        stage ('demo-preview-tusker') {
            when {
                // Only say hello if a "greeting" is requested
                expression { params.REQUESTED_ACTION == 'tusker' || params.REQUESTED_ACTION == 'all' }
            }
            steps {
                echo 'Depoying demo-preview-tusker'
                
                sh "cd ${PLAYBOOK_PATH} && cp ~/ansible.cfg ansible.cfg && sudo ansible-playbook -i ${PLAYBOOK_PATH}/inventory/demo-preview ${PLAYBOOK_PATH}/tusker.yml --tags update --vault-password-file  ~/.agv"
                
            }
        }
        stage ('demo-preview-pheme') {
            when {
                // Only say hello if a "pheme" is requested
                expression { params.REQUESTED_ACTION == 'pheme'  || params.REQUESTED_ACTION == 'all'}
            }
            steps {
                echo 'Depoying demo-preview-cascade'
                
                sh "cd ${PLAYBOOK_PATH}/../pheme && cp ~/ansible.cfg ansible.cfg && sudo ansible-playbook -i ${PLAYBOOK_PATH}/../pheme/inventory/demo-preview ${PLAYBOOK_PATH}/../pheme/pheme.yml --tags update --vault-password-file  ~/.agv"
                
            }
        }
        stage ('demo-preview-droms') {
            when {
                // Only say hello if a "droms" is requested
                expression { params.REQUESTED_ACTION == 'droms'  || params.REQUESTED_ACTION == 'all'}
            }
            steps {
                echo 'Depoying demo-preview-cascade'
                
                sh "cd ${PLAYBOOK_PATH} && cp ~/ansible.cfg ansible.cfg && sudo ansible-playbook -i ${PLAYBOOK_PATH}/inventory/demo-preview ${PLAYBOOK_PATH}/droms.yml --tags update --vault-password-file  ~/.agv"
                
            }
        }
        stage ('demo-preview-openadr2b') {
            when {
                // Only say hello if a "greeting" is requested
                expression { params.REQUESTED_ACTION == 'openadr2b' || params.REQUESTED_ACTION == 'all' }
            }
            steps {
                echo 'Depoying openadr2b'
                
                sh "cd ${PLAYBOOK_PATH} && cp ~/ansible.cfg ansible.cfg && sudo ansible-playbook -i ${PLAYBOOK_PATH}/inventory/demo-preview ${PLAYBOOK_PATH}/openadr2b.yml  --tags update --vault-password-file  ~/.agv"
            }
        }
        stage ('demo-preview-ceep') {
            when {
                // Only say hello if a "ceep" is requested
                expression { params.REQUESTED_ACTION == 'ceep' || params.REQUESTED_ACTION == 'all' }
            }
            steps {
                echo 'Depoying demo-preview-cascade'
                
                sh "cd ${PLAYBOOK_PATH} && cp ~/ansible.cfg ansible.cfg && sudo ansible-playbook -i ${PLAYBOOK_PATH}/inventory/demo-preview ${PLAYBOOK_PATH}/ceep.yml --tags update --vault-password-file  ~/.agv"
                
            }
        }
        stage ('demo-preview-dianoga') {
            when {
                // Only say hello if a "greeting" is requested
                expression { params.REQUESTED_ACTION == 'dianoga' || params.REQUESTED_ACTION == 'all' }
            }
            steps {
                echo 'Depoying  on demo-preview-dianoga'
                
                sh "cd ${PLAYBOOK_PATH} && cp ~/ansible.cfg ansible.cfg && sudo ansible-playbook -i ${PLAYBOOK_PATH}/inventory/demo-preview ${PLAYBOOK_PATH}/dianoga.yml --tags update --vault-password-file  ~/.agv"
                
            }
        }
        stage ('demo-preview-rtcc') {
            when {
                // Only say hello if a "greeting" is requested
                expression { params.REQUESTED_ACTION == 'rtcc' || params.REQUESTED_ACTION == 'all' }
            }
            steps {
                echo 'Depoying demo-preview-rtcc'
                
                sh "cd ${PLAYBOOK_PATH} && cp ~/ansible.cfg ansible.cfg && sudo ansible-playbook -i ${PLAYBOOK_PATH}/inventory/demo-preview ${PLAYBOOK_PATH}/rtcc.yml -e deploy_env=qa05 --tags update --vault-password-file  ~/.agv"
                
            }
        }
        stage ('demo-preview-cascade') {
            when {
                
                expression { params.REQUESTED_ACTION == 'cascade' || params.REQUESTED_ACTION == 'all' }
            }
            steps {
                echo 'Depoying demo-preview-cascade'
                
                sh "cd ${PLAYBOOK_PATH} && cp ~/ansible.cfg ansible.cfg && sudo ansible-playbook -i ${PLAYBOOK_PATH}/inventory/demo-preview ${PLAYBOOK_PATH}/cascade.yml --tags update --vault-password-file  ~/.agv"
                
            }
        }
        stage ('demo-preview-fam-backend') {
            when {
                
                expression { params.REQUESTED_ACTION == 'fam-backend' || params.REQUESTED_ACTION == 'all' }
            }
            steps {
                echo 'Depoying demo-preview-fam-backend'
                
                sh "cd ${PLAYBOOK_PATH} && cp ~/ansible.cfg ansible.cfg && sudo ansible-playbook -i ${PLAYBOOK_PATH}/inventory/demo-preview ${PLAYBOOK_PATH}/fam-backend.yml  --tags=configs,restart --vault-password-file  ~/.agv"
                
            }
        }
        
        
        
    }
}

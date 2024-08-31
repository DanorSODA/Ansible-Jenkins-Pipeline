pipeline {
    agent any
    parameters {
        string(name: 'HOST_IP', defaultValue: '', description: 'IP address of the remote host')
        string(name: 'USERNAME', defaultValue: '', description: 'Username for the remote host')
        password(name: 'PASSWORD', defaultValue: '', description: 'Password for the remote host user')
        string(name: 'SSH_KEY', defaultValue: '', description: 'SSH Key for the remote host')
        string(name: 'SERVER_NAME', defaultValue: '', description: 'Server name or IP address for Nginx')
        string(name: 'MYSQL_ROOT_PASSWORD', defaultValue: '', description: 'Root password for MySQL')
    }
    stages {
        stage('Setup Host') {
            steps {
                script {
                    writeFile file: 'ansible/hosts', text: "[target]\n${params.HOST_IP} ansible_ssh_user=${params.USERNAME} ansible_ssh_pass=${params.PASSWORD}"

                    ansiblePlaybook(
                        playbook: 'ansible/playbook.yml',
                        inventory: "ansible/hosts",
                        extras: "-e host_ip=${params.HOST_IP} -e username=${params.USERNAME} -e password=${params.PASSWORD} -e ssh_key=${params.SSH_KEY} -e server_name=${params.SERVER_NAME} -e mysql_root_password=${params.MYSQL_ROOT_PASSWORD}",
                        installation: 'Ansible'
                    )
                }
            }
        }
    }
}

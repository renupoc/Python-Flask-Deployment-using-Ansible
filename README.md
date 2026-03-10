"# Python-Flask-Deployment-using-Ansible and deployed using jenkins"
Pipeline :

pipeline{
    agent any
    stages{
        stage("checkout"){
            steps{
                git branch: 'main',
                url: "https://github.com/renupoc/Python-Flask-Deployment-using-Ansible.git"
            }
        }
        stage("deploy"){
            steps{
                sh  'ansible-playbook -i inventory playbook.yml'
            }
        }
    }
}

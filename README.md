"# Python-Flask-Deployment-using-Ansible and deployed using jenkins pipeline
LAMP : LAMP stack is a web development stack which consists Linux as an operating system and Apache as a web server and mysql as a database and Python or PHP as a programming Language."
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

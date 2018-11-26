node{
  stage('SCM Checkout'){
    git 'https://github.com/naveens1726/devopsPipeline'
  }
  stage('Compile-Package'){
      def M2_Home =  tool name: 'Maven-3', type: 'maven'   
      sh "${M2_Home}/bin/mvn package -DskipTests=true"
  }
  stage('Copy WAR file'){
     sh 'cp ./target/myweb-0.0.4.war ./roles/Deploy/files/myweb-0.0.4.war'
  }
  stage('Ansible-deploy'){
     sh 'ansible-playbook -i /home/naveens1726/ansible/hosts Start.yml'
  }
}

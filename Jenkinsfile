node{
  stage('SCM Checkout'){
    git 'https://github.com/naveens1726/devopsPipeline'
  }
  stage('Compile-Package'){
      def M2_Home =  tool name: 'Maven-3', type: 'maven'   
      sh "${M2_Home}/bin/mvn package -DskipTests=true"
  }
}

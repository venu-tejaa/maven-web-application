node {
    
    def mavenHome = tool name : "maven3.9.9"
    stage('checkoutcode'){
        git branch: 'development', credentialsId: '69f42c01-e6c4-46d6-b81b-acf46114accf', url: 'https://github.com/venu-tejaa/maven-web-application.git'
    }
    
    stage('build'){
        sh "${mavenHome}/bin/mvn clean package"
    }
    
    stage('UploadArtifactIntonexus'){
        sh "${mavenHome}/bin/mvn clean deploy"
    }
   /* stage('depoytoTomact'){
        sshagent(['a75a3172-ef93-4681-a79b-7457974a9644']) {
     sh "scp  -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@172.31.33.64:/opt/tomcat9/webapps/"
}
    } */
}

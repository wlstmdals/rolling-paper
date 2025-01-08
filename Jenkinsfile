 node {
     stage('Clone repository') {
         git credentialsId: 'git_access_token', url: 'https://github.com/wlstmdals/rolling-paper.git'
     }
     stage('Build image') {
         dockerImage = docker.build("sushijin/node-front:1.0")
     }
     stage('Push image') {
         withDockerRegistry([credentialsId: "docker-access", url: ""]) {
             dockerImage.push()
         }
     }
 }


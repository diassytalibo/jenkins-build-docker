node {
  def app

    stage('Clone') {
	checkout scm
    }

    stage('Build image') {
	app = docker.build("dia/nginx")
    }
    stage('Run') {
	docker.image('dia/nginx').withRun('-p 80:80') { c ->
        sh 'docker ps'
        sh 'curl localhost'
    }
    }
}

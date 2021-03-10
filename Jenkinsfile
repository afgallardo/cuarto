pipeline{
    agent any
    stages{
        stage('Clonando Repositorio'){
            steps{
                sh 'echo "Clonando Repositorio"'
		git url: 'https://github.com/afgallardo/cuarto.git' 
            }
        }
        stage('Compilando Codigo Fuente'){
           steps {
                sh '''
			bash -c "echo "Compilando Codigo Fuente""
			bash -c "gcc /var/lib/jenkins/workspace/pipeline-con-jenkinsfile-desde-repositorio/fuente.c -o /tmp/binario"
		   '''
           }
        }
        stage('Probando Aplicacion') {
           steps {
                sh 'echo "Probando Aplicacion..."'
                sh '/tmp/binario'
           }
        }

	stage('Docker Build') {
	   steps {
		sh 'echo "Generando Imagen de Aplicacion..."'
	   }
	}
	
	stage('Subiendo Imagen a Docker Hub') {
	   steps {
		sh 'echo "Docker push de Imagen to Docker Hub..."'
	   }
	}
    }
} 

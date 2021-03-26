pipeline{
   agent{label 'master'}
   stages{
	stage('Clonando Proyecto desde Repositorio'){
	   steps{
		sh 'echo "Clonando Proyecto desde Repositorio"'
		git url: 'http://github.com/afgallardo/cuarto.git'
	}}
	stage('Compilando Codigo'){
	   steps{
		sh 'echo "Compilando Codigo"'
		sh 'gcc /var/lib/jenkins/workspace/pipeline-con-jenkinsfile-desde-repositorio-appc/fuente.c -o /tmp/appc/appc-v4'
	}}
	stage('Probando Aplicacion'){
	   steps{
		sh 'echo "Probando Aplicacion"'
		sh '/tmp/appc/appc-v4'
	}}
	stage('Generando Imagen de Contenedor de la Aplicacion'){
	   steps{
		sh 'echo "Generando Imagen de Contenedor de la Aplicacion"'
	}}
	stage('Subiendo Imagen de Contenedor al Conteiner Registry'){
	   steps{
		sh 'echo "Subiendo Imagen de Contenedor al Conteiner Registry"'
	}}
 }
   post{
	always{
		sh 'echo "Esto se ejecuta SIEMPRE"'
	}
	failure{
		sh 'echo "Esto se ejecuta ante un FALLO"'
	}
	success{
		sh 'echo "Esto se ejecuta ante un EXITO"'
	}
 }
}

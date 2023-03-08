pipeline {
agent{
label{
		label "built-in"
		customWorkspace "/mnt/data/pipeline"
}
}

stages {

		stage ("on master"){
			steps {
					sh "yum install tree -y"
			}
		
		}
		
		stage ("on slave"){
		agent {
		node {
				label "slave"
				customWorkspace "/mnt/data/slavepipeline"
		}
		
		}
		
		steps {
				sh "sudo yum install httpd -y"
				sh "sudo service httpd start"
		
		}
		
		}
		stage ("on slave 2"){
		agent {
		node {
				label "slave2"
				customWorkspace "/mnt/data/slave2pip"
		}
		
		}
		
		steps {
				sh "sudo yum install git -y"
		
		}
		
		}

}

}

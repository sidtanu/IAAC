node {

    stage ('checkout') {

        echo "test test    mm"
	checkout scm
    }
    stage ('setupenv') {
    	echo " - - - - Setting up environment now - - - - "
	////bin////sh setupenv.sh
    }

    stage ('TerraformActivity') {
    	echo " - - - - Ready to execute Terraform now - - - - "
	sh '''
	cd TF
	
	 /opt/apps/vault --version
	 /opt/apps/vault kv get -field="foo" secret/hello
	
	 echo `./terraform --version`


	'''
	}
}

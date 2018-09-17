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
	 export VAULT_ADDR='http://127.0.0.1:8200'
	 export VAULT_TOKEN="80b097e3-ca1a-b713-2328-70da1e8562cc"
	 
	 /opt/apps/vault --version
	 /opt/apps/vault kv get -field="foo" secret/hello
	
	 echo `./terraform --version`


	'''
	}
}

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
	
	az login --service-principal -u "`vault kv get -field="client_id" secret/wrtazr`" -p "`vault kv get -field="client_secret" secret/wrtazr`" --tenant "`vault kv get -field="tenant_id" secret/wrtazr`"
	
	 echo `./terraform --version`
	 ./terraform init
	 ./terraform plan
	 ./terraform apply -var "adminPassword=Thankyou@1"
	 
	 echo " - - - - - - C O M P L E T E D - - - - - - - "


	'''
	}
}

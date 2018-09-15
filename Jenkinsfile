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
	
	 wget -q https://releases.hashicorp.com/terraform/0.11.8/terraform_0.11.8_linux_amd64.zip | -y
	 unzip terraform_0.11.8_linux_amd64.zip
	
	 echo `./terraform --version`

	./terraform init
	./terraform plan
	./terraform apply -var "adminPassword=Thankyou@1"
	'''
	}
}

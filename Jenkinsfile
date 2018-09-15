node {

    stage ('checkout') {

        echo "test test"
	checkout scm
    }
    stage ('setupenv') {
    	echo " - - - - Setting up environment now - - - - "
	////bin////sh setupenv.sh
    }

    stage ('TerraformActivity') {
    	echo " - - - - Ready to execute Terraform now - - - - "
	cd TF
	terraform init
	terraform plan
	terraform apply
	}
}

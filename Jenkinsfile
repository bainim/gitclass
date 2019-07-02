pipeline {
        agent any
	            stages {
				        stage ('One') {
						         steps {
								     echo 'This is Devops Team'
								 }
						}
						stage ('Two') {
						         steps {
								 input ('Do you want to procees')
								 }
						}
						stage ('Three') {
						          when {
								      ko {
									    branch "master"
									  }      
								  }
								  steps {
								     echo 'Hello Every one'
								  }
						}
						stage ('Four') {
						   parallel {   // This directive allows you to run nested stages in  parallel
						     stage ('UNIT TESTS') {
						           steps {
								       echo "Running the unit Tets.."
								   }
						     }
							 stage (Integration Tests) {
							     agent { // This docker agent will execute the ‘Integration test’ stage
								    docker {
									   reuseNode true
									   image 'ubuntu'
									}
								 }
								 steps {
								     echo "Running the Integration Tests..."
								 }
							 }
						   }
						}
						
				}
}
#!groovy
import groovy.json.JsonSlurperClassic
node {

    def SF_CONSUMER_KEY_SIT='3MVG9wt4IL4O5wvI.yI7M89fObHLexE98bMda7.JUK7.jleW3LAOieskNa5gql7ZJsUpJOkqMB8JJdv8iQZuB'
    def SF_USERNAME_SIT='abinayab@deloitte.com'
    def SERVER_KEY_CREDENTIALS_ID='8950126e-0838-443c-9694-d767b2ad66dd'
    def SF_INSTANCE_URL = 'https://login.salesforce.com'

    

    def toolbelt = tool 'toolbelt'
   
	

      withCredentials([file(credentialsId: SERVER_KEY_CREDENTIALS_ID, variable: 'server_key_file')]) {
	//stages {
	    
        stage('Installation') {
          
         // println ('Inside Installation Stage')
               
		    rc = bat returnStatus: true, script: "\"${toolbelt}\" force:auth:jwt:grant --clientid ${SF_CONSUMER_KEY_SIT} --username ${SF_USERNAME_SIT} --jwtkeyfile \"${server_key_file}\" --setalias SIT --instanceurl ${SF_INSTANCE_URL}"
		    
            bat returnStatus: true, script: "\"${toolbelt}\" force:org:list"

        }
	    
	    

        

//}
}
 
}
import groovy.json.JsonSlurperClassic
import groovy.json.*
pipeline {
  agent any
  stages {
      stage('readCustomerFile') {
      steps {
        echo 'Reading file'
        readFile 'customer.json'
        script {
          def customer = readFile(file:'customer.json')
          def custdata = new JsonSlurperClassic().parseText(customer)

          env.ENV_VAR1 = "${custdata.customers[0].name}"
          env.ENV_VAR2 = "${custdata.customers[0].location}"

          echo "dev-hostname: ${custdata.customers[0].name}"
          echo "dev-hostname: ${custdata.customers[0].location}"

          echo "dev-hostname: ${custdata.customers[0].lifecycle[0].name}"
          echo "dev-hostname: ${custdata.customers[0].lifecycle[0].description}"

          echo "dev-hostname: ${custdata.customers[0].lifecycle[0].app_servers[0].hostname}"
          echo "dev-hostname: ${custdata.customers[0].lifecycle[0].app_servers[0].ip_address}"

          echo "dev-hostname: ${custdata.customers[0].lifecycle[0].app_servers[1].hostname}"
          echo "dev-hostname: ${custdata.customers[0].lifecycle[0].app_servers[1].ip_address}"

          echo "dev-hostname: ${custdata.customers[0].lifecycle[0].db_servers[0].hostname}"
          echo "dev-hostname: ${custdata.customers[0].lifecycle[0].db_servers[0].ip_address}"
          echo "dev-hostname: ${custdata.customers[0].lifecycle[0].db_servers[0].db_name}"
          echo "dev-hostname: ${custdata.customers[0].lifecycle[0].db_servers[0].port}"
          echo "dev-hostname: ${custdata.customers[0].lifecycle[0].db_servers[0].user_name}"

        }
        sh 'echo "### ENV_VAR1 $ENV_VAR1"'
        sh 'echo "### ENV_VAR2 $ENV_VAR2"'
      }
    }
  }
}

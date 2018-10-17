pipeline {
  agent {
    node {
      label 'dcust-bastion'
    }

  }
  stages {
    stage('Get Detail') {
      steps {
        echo '"Customer Name: ${params.CUST_NAME}"'
      }
    }
  }
  parameters {
    choice(name: 'CUST_NAME', choices: '''dcust
abc
xyz
aaa''', description: 'Enter Customer name ?')
    choice(name: 'LIFE_CYCLE', choices: '''dev
tst
stg
uat''', description: 'Enter Life cycle name ?')
    string(name: 'SFTP_FILE_PATH', defaultValue: 'BambooRoseTradeEngines-2017R1FP36-Tomcat.zip', description: 'Artifact to be downloaded')
    booleanParam(name: 'UPGRADE_DB_Q', defaultValue: true, description: 'Upgrade DB?')
  }
}
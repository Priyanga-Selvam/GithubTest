pipeline{
  agent any
  parameters{
    choice(name: 'VERSION',choices:['1.1.0','1.2.0','1.3.0'],description:'')
    booleanParam(name:'executeTests',defaultValue: true,description:'')
  }
  stages{
    stage("build"){
      steps{
        echo 'Building the Application.....'
      }
    }
    stage("test"){
      when{
        expression{
          params.executeTests
        }
      }
      steps{
        echo 'Testing the Application.....'      
      }
    }
    stage("deploy"){
      steps{
        echo 'Deploying the Application.....'
        echo "Deploying version ${params.VERSION}"
      }
    }
  }
}

pipeline{
    agent any
    parameters{
        choice(name:'version',choices:['1.1.0','1.2.0','1.3.0'],description:'deploy to staging server')
        booleanParam(name:'executeTests',defaultValue:true,description:'')
    }
    stages{
        stage("build"){
            steps{
                echo 'Building app'
            }
        }
         stage("test"){
            steps{
                echo 'testing app'
            }
        }
         stage("publish"){
            steps{
                echo 'publishing app'
                echo "publishing version ${params.version}"
            }
        }
      
    }
}


  

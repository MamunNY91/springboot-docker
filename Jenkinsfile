def gv
pipeline{
    agent any
    parameters{
        choice(name:'version',choices:['1.1.0','1.2.0','1.3.0'],description:'deploy to staging server')
        booleanParam(name:'executeTests',defaultValue:true,description:'')
    }
    stages{

         stage("init"){
            steps{
                script{
                    gv = load "./script.groovy"
                }
            }
        }

        stage("build"){
            steps{
                script{
                    gv.buildApp()
                }
            }
        }
         stage("test"){
            when{
                expression{
                    params.executeTests
                }
            }
            steps{
                script{
                    gv.testApp()
                }
            }
        }
         stage("publish"){
            steps{
                script{
                    gv.deployApp()
                }

                echo "publishing version ${params.version}"
            }
        }
      
    }
}


  

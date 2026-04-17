pipeline { 
     agent any 
     stages { 
          stage("Compile") { 
               steps { 
                    sh "./gradlew compileJava" 
               } 
          } 
          stage("Unit test") { 
               steps { 
                    sh "./gradlew test" 
               } 
          }
          stage("Code coverage") { 
               steps { 
                    sh "./gradlew jacocoTestReport" 
                    sh "./gradlew jacocoTestCoverageVerification"
                    sh "./gradlew jacocoTestReport"
                    publishHTML (target: [
                         reportName: 'Code Coverage Report',
                         reportDir: 'build/reports/jacoco/test/html',
                         reportFiles: 'index.html'
                    ])
               } 
          } 
     } 
} 

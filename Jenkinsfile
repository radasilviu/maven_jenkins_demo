pipeline {
   agent any
   stages{
      stage('Maven Build + Artifactory Upload') {
                  steps {
                      rtMavenRun (
                          // The tool name of maven is defined in Jenkins Configurations
                          tool: 'MavenJenkins',
                          pom: 'pom.xml',
                          // Maven build command
                          // Debug Mode
                          //goals: 'clean install ${maven_proxy} -X -Dmaven.test.skip=true',
                          // Force Artifactory Update
                          // goals: 'clean install ${maven_proxy} -U -Dmaven.test.skip=true',
                          // Full Stack Trace
                          // goals: 'clean install ${maven_proxy} -e -Dmaven.test.skip=true',
                          goals: 'clean install -Dmaven.test.skip=true',
                          deployerId: "MAVEN_DEPLOYER",
                          resolverId: "MAVEN_RESOLVER"
                      )
                  }
      }
   }

}
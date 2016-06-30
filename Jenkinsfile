#!groovy

node {
   // Mark the code checkout 'stage'....
   stage 'Checkout'

   // Get some code from a GitHub repository
   git url: 'https://github.com/BraintagsGmbH/BtBase.git'

   // Get the maven tool.
   // ** NOTE: This 'M3' maven tool must be configured
   // **       in the global configuration.           
   def mvnHome = tool 'M3'
   env.PATH = "${mvnHome}/bin:${env.PATH}"

   // Mark the code build 'stage'....
   stage 'Build'
   // Run the maven build
   sh "mvn -Dsign.skip=true  clean deploy"

}
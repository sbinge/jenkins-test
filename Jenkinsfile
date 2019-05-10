#!groovy

node('node') {
    currentBuild.result = "SUCCESS"

    try {
        stage('Checkout'){
            checkout scm
        }

        stage('BuildDebug'){
            println "  (env) Build URL : ${env.BUILD_URL}"
            println " (env) Build node : ${env.NODE_NAME}"
            println " Master host name : " + Jenkins.getInstance().getComputer('').getHostName()
            println "-----"
            println "        Node name : " + Jenkins.getInstance().getComputer(env['NODE_NAME']).getName()
            println "   Node host name : " + Jenkins.getInstance().getComputer(env['NODE_NAME']).getHostName()
            println "         Node URL : " + Jenkins.getInstance().getComputer(env['NODE_NAME']).getUrl()
            println "-----"
            println "Current node name : " + Jenkins.getInstance().currentComputer().getName()
            println "Current host name : " + Jenkins.getInstance().currentComputer().getHostName()
            println " Current node URL : " + Jenkins.getInstance().currentComputer().getUrl()
        }
    } catch (err) {
        currentBuild.result = "FAILURE"
        throw err
    }
}

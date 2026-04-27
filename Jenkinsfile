@Library('jenkins-shared-library') _

def configMap = [
    project: "roboshop",
    component: "catalogue"
]

echo "Going to execute Jenkins shared library"

if ( ! env.BRANCH_NAME.equalsIgnoreCase('main') ){
    nodeJSEKSPipeline(configMap)
}
else {
    echo "Please follow the CR process"
}
<<<<<<< HEAD
@Library('jenkins1-shared-library') _

def configMap = [
    project: "roboshop",
    component: "catalogue-CC"
=======
@Library('jenkins-shared-library') _

def configMap = [
    project: "roboshop",
    component: "catalogue
>>>>>>> 33d111328a51269e2eda6abaccbc63229b57d9a0
]

echo "Going to execute Jenkins shared library"
// if branch is not equal to main, then run CI pipeline
if ( ! env.BRANCH_NAME.equalsIgnoreCase('main') ){
    nodeJSEKSPipeline(configMap)
}
else {
    echo "Please follow the CR process"
}
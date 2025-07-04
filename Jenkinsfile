#!groovy
@Library('roboshop-shared-library') _

// Define component and application type
def configMap = [
    application: "nodejsVM",
    component: "catalogue"
]

// Ensure branch name is available and handle non-main branches
def branch = env.BRANCH_NAME ?: env.GIT_BRANCH?.replaceAll('origin/', '') ?: 'unknown'
echo "Triggered by branch: ${branch}"

if (!branch.equalsIgnoreCase('main')) {
    pipelineDecission.decidePipeline(configMap)
} else {
    echo "This is PRODUCTION. Please follow the CR (Change Request) process."
}
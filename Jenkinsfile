/* groovylint-disable CatchError, CatchException, CompileStatic, DuplicateStringLiteral, LineLength, NestedBlockDepth, NoDef, UnnecessaryCatchBlock, UnnecessaryObjectReferences, VariableTypeRequired */
try {
    node {
            cleanWs()

            stage('Clone Repository')
            {
                final scmVars = checkout(scm)
                env.BRANCH_NAME = scmVars.GIT_BRANCH
                env.SHORT_COMMIT = "${scmVars.GIT_COMMIT[0..7]}"
                env.REPO_NAME = scmVars.GIT_URL.replaceFirst(/^.*\/([^\/]+?).git$/, '$1')
                env.IMAGE = "${env.REPO_NAME}:uat-${env.SHORT_COMMIT}"
                env.IMAGE_REPO_NAME = 'https://957907570595.dkr.ecr.us-east-2.amazonaws.com'
                env.ECR_URL = "${env.IMAGE_REPO_NAME}/${env.REPO_NAME}:${env.SHORT_COMMIT}"
                echo "Branch name: ${env.BRANCH_NAME}"
                echo "Short commit: ${env.SHORT_COMMIT}"
                echo "Repo name: ${env.REPO_NAME}"
                echo "Image path: ${env.ECR_URL}"
                env.ECRCRED = 'ecr:us-east-2:c5e37e9f-92b6-4760-8722-ca1865a1ebad'
            }

            

            //TODO - rm i imagename:tag
        
    }
    } catch (Error| Exception e) {
    throw e
    /* groovylint-disable-next-line EmptyFinallyBlock */
    } finally {
}

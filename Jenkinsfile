pipeline {
    agent any

    environment {
        GITHUB_CREDENTIALS = credentials('mrsandyy')
        REPO_URL = 'https://github.com/mrsandyy/subodh-bca-resources.git'
    }

    stages {
        stage('Clone Repository') {
            steps {
                git credentialsId: 'github-credentials-id',
                    url: env.REPO_URL,
                    branch: 'main'
            }
        }

        stage('Convert Markdown to PDF') {
            steps {
                script {
                    // Use Jenkins workspace as the base path
                    def workspacePath = env.WORKSPACE

                    // Find all directories containing markdown files, excluding root
                    def mdFolders = sh(
                        script: """
                            find ${workspacePath} -type d -not -path '*/\.*' | while read -r dir; do
                                if [ "$(find "$dir" -maxdepth 1 -name '*.md')" ]; then
                                    echo "$dir"
                                fi
                            done
                        """,
                        returnStdout: true
                    ).trim().split('\n')

                    // Process each folder with markdown files
                    mdFolders.each { folder ->
                        // Find markdown files in this folder
                        def mdFiles = sh(
                            script: "find '${folder}' -maxdepth 1 -name '*.md'",
                            returnStdout: true
                        ).trim().split('\n')

                        mdFiles.each { mdFile ->
                            // Get parent directory of the current folder
                            def parentDir = new File(folder).getParent()

                            // Generate PDF filename in the parent directory
                            def pdfFileName = new File(mdFile).getName().replace('.md', '.pdf')
                            def pdfFile = "${parentDir}/${pdfFileName}"

                            // Convert markdown to PDF
                            sh """
                                mkdir -p \$(dirname "${pdfFile}")
                                pandoc "${mdFile}" -o "${pdfFile}" \
                                --pdf-engine=pdflatex \
                                --variable geometry=margin=1in
                            """
                        }
                    }
                }
            }
        }

        stage('Commit PDFs') {
            steps {
                script {
                    sh '''
                        git config user.email "sandeephbishnoi29@gmail.com"
                        git config user.name "mrsandyy"
                        git add .
                        git diff-index --quiet HEAD || git commit -m "Auto-generate PDFs from Markdown files"
                        git push
                    '''
                }
            }
        }
    }

    post {
        success {
            echo 'PDFs generated and committed successfully!'
        }
        failure {
            echo 'Pipeline failed. Check logs for details.'
        }
    }
}

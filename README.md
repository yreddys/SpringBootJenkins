**The goal you specified requires a project to execute but there is no POM in this directory**




stage('BuildMaven') {
            when {
                expression { params.action == 'create' }
            }
            steps {
                // Navigate to the project directory
                dir("${params.AppName}") {
                    // Run Maven commands with -DskipTests option
                    sh "mvn compile -f $workspace/pom.xml"
                }


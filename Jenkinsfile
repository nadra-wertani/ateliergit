pipeline {
    agent any

    tools {
        jdk 'JAVA_HOME'
        maven 'M2_HOME'
    }

    stages {
        stage ('Compile Stage') {
            steps {
                sh 'mvn clean compile'
            }
        }

        /* Décommente ce bloc si tu veux activer l'analyse SonarQube */
        /*
        stage('SonarQube Analysis') {
            steps {
                sh 'mvn sonar:sonar -Dsonar.login=squ_99b9e849f7f85fb4105915f6375e6abdd2da4177 -Dmaven.test.skip=true'
            }
        }
        */

        stage('MVN Nexus') {
            steps {
                sh 'mvn deploy -Dmaven.test.skip=true'
            }
        }
    } // <- Cette accolade ferme correctement le bloc "stages"
} // <- Cette accolade ferme correctement le bloc "pipeline"

pipeline {
    agent any
    
    environment {
        // Tu peux définir des variables d'environnement ici
        GIT_REPO = 'https://github.com/hadjouAmar/Spring-Rest-API-Unit-Test.git'
    }
    
    stages {
        stage('Checkout') {
            steps {
                // Cloner le code depuis GitHub
                git url: "$GIT_REPO", branch: 'master' // Remplace 'main' par le nom de ta branche
            }
        }
        
        stage('Install Dependencies (Step 1)') {
            steps {
                // Installer les dépendances (exemple avec Maven)
                sh 'mvn clean install -DskipTests'
            }
        }

        stage('Install Dependencies (Step 2)') {
            steps {
                // Installer les dépendances avec Maven (ou des étapes supplémentaires)
                sh 'mvn clean install -DskipTests'
            }
        }

        stage('Run Tests') {
            steps {
                // Exécuter les tests avec Maven
                sh 'mvn test'
            }
        }

        stage('Build') {
            steps {
                // Construire le projet avec Maven
                sh 'mvn package'
            }
        }

        stage('Deploy') {
            steps {
                // Étape de déploiement (optionnelle)
                echo 'Déploiement de l\'application'
            }
        }
    }

    post {
        always {
            // Action après l'exécution du pipeline (ex: nettoyage, notification)
            echo 'Pipeline terminé'
        }
        success {
            // Action en cas de succès
            echo 'Pipeline réussi'
        }
        failure {
            // Action en cas d'échec
            echo 'Pipeline échoué'
        }
    }
}

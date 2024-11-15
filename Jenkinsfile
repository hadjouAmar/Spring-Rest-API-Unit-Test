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
                git url: "$GIT_REPO", branch: 'main' // Remplace 'main' par le nom de ta branche
            }
        }
        
        stage('Install Dependencies') {
            steps {
                // Installer les dépendances (exemple avec npm pour un projet Node.js)
                sh 'npm install'
            }
        }

        stage('Run Tests') {
            steps {
                // Exécuter les tests (ici avec npm)
                sh 'npm test'
            }
        }

        stage('Build') {
            steps {
                // Construire le projet (par exemple, avec npm)
                sh 'npm run build'
            }
        }
        
        stage('Deploy') {
            steps {
                // Ici, tu peux ajouter une étape de déploiement si tu veux
                echo 'Déploiement de l\'application'
            }
        }
    }

    post {
        always {
            // Actions à faire après l'exécution du pipeline (ex: nettoyage, notification)
            echo 'Pipeline terminé'
        }
        success {
            // Action en cas de succès (par exemple, envoyer une notification)
            echo 'Pipeline réussi'
        }
        failure {
            // Action en cas d'échec (par exemple, envoyer une alerte)
            echo 'Pipeline échoué'
        }
    }
}

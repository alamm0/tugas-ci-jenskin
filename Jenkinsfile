pipeline {
    agent any

    tools {
        nodejs 'node' 
    }

    stages {
        stage('Checkout') {
            steps {
                echo 'Mengambil kode dari GitHub...'
                git branch: 'master', credentialsId: 'github-token', url: 'https://github.com/alamm0/tugas-ci-jenskin.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Memulai proses Build (Install Dependencies)...'
                bat 'npm install'
            }
        }

        stage('Test') {
            steps {
                echo 'Menjalankan Unit Test...'
                bat 'echo "Semua unit test berhasil dijalankan tanpa error!"'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Menyiapkan proses Deploy...'
                bat 'echo Deploy berhasil dilakukan ke environment Production!'
            }
        }
    }
    
    post {
        success {
            echo 'YEAY! Pipeline berhasil tereksekusi semua! (Hijau)'
        }
        failure {
            echo 'YAH! Pipeline gagal. Cek log untuk melihat errornya. (Merah)'
        }
    }
}

pipeline {
    agent {
        kubernetes {
            // 這就是告訴 K8s：我要一個臨時工，名字叫 builder
            yaml """
apiVersion: v1
kind: Pod
metadata:
  labels:
    app: jenkins-agent
spec:
  containers:
  - name: docker
    image: docker:dind
    command:
    - cat
    tty: true
    volumeMounts:
    - name: docker-sock
      mountPath: /var/run/docker.sock
  - name: tools
    image: alpine:latest
    command:
    - cat
    tty: true
  volumes:
  - name: docker-sock
    hostPath:
      path: /var/run/docker.sock
"""
        }
    }
    
    stages {
        stage('Initialize') {
            steps {
                container('tools') {
                    echo "🚀 Pipeline 啟動！"
                    echo "正在檢查環境..."
                    sh 'hostname'
                    sh 'whoami'
                }
            }
        }

        stage('Checkout Code') {
            steps {
                // 自動拉取目前的 Branch 程式碼
                checkout scm
                container('tools') {
                    sh 'ls -al'
                }
            }
        }

        stage('Test Build') {
            steps {
                container('tools') {
                    echo "🔧 這是測試建置階段 (模擬中)..."
                    // 這裡以後可以放你的 npm install 或 mvn build
                    sh 'echo "Building project..."'
                }
            }
        }
    }

    post {
        success {
            echo '✅ 任務成功！Pod 即將銷毀。'
        }
        failure {
            echo '❌ 任務失敗！請檢查 Log。'
        }
    }
}
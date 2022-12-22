node{
          
          def remote = [:]
          remote.name = 'test'
          remote.host = '172.27.11.10'
          //remote.password = 'hst123@@'
          remote.user = 'root'
          remote.allowAnyHosts = true
          
          stage('Testando Conexão SSH') {
            sshCommand remote: remote, command: "ls -lrt"
            sshCommand remote: remote, command: "whoami"
          }
}

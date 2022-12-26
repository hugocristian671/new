pipeline {
    agent any
    parameters {
        checkboxParameter(name: 'Platforms1', format: 'JSON',
                pipelineSubmitContent: '{"CheckboxParameter": [{"key": "NT","value": "NT"},{"key": "LINUX","value": "LINUX"},{"key": "UNIX","value": "UNIX"}]}', description: '')
        checkboxParameter(name: 'Platforms2', format: 'YAML',
                pipelineSubmitContent: "CheckboxParameter: \n  - key: monday\n    value: monday\n  - key: tuesday\n    value: tuesday\n", description: '')
    }
    stages {
        stage('BD') {
            steps {
                script{
                    switch(params.Platforms1){
                        case "NT": echo "I'M NT"; break
                        case "LINUX": echo "I'M LINUX"; break
                        case "UNIX": echo "I'M UNIX"; break
                    }
                }
            }
        }
    }
}

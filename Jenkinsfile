properties([
  parameters([
    [$class: 'CascadeChoiceParameter', 
      choiceType: 'PT_CHECKBOX', 
      description: 'Select Environment',
      filterLength: 1,
      filterable: false,
      name: 'Environment', 
      script: [
        $class: 'GroovyScript', 
        script: [
          classpath: [], 
          sandbox: false, 
          script: 
            'return[\'Development\',\'QA\',\'Staging\',\'Production\']'
        ]
      ]
    ]
  ])
])
 
pipeline {
  agent any
  stages {
    stage('Check env') {
      steps {
        script {
          if ( env.Environment.isEmpty() ) {
            echo "Environment not specified."
            autoCancelled = true
            error('Aborting the build.')
          }
          else {
            echo "Environment total: ${env.Environment}"
            String[] Env_Array = "${params.Environment}".split(',');
            for (x in Env_Array) {
              echo "ENV: ${x}"
            }
          }
        }
      }
    }
  }
}

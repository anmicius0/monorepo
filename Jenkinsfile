pipeline {
    agent any
    stages {
        stage('Nexus Policy Evaluation') {
            steps {
                nexusPolicyEvaluation(
                    advancedProperties: '',
                    enableDebugLogging: false,
                    failBuildOnNetworkError: false,
                    failBuildOnScanningErrors: false,
                    iqApplication: selectedApplication('monorepo'),
                    iqInstanceId: 'default-iqserver',
                    iqOrganization: '74d58a9a10e24d62a13e51532a3216cb',
                    iqStage: 'develop',
                    jobCredentialsId: '',
                    iqScanPatterns: [
                        [scanPattern: '**/*.tar.gz'],
                        [scanPattern: '**/*.zip'],
                        [scanPattern: '**/*.jar'],
                        [scanPattern: '**/*.ear'],
                        [scanPattern: '**/*.war'],
                        [scanPattern: '**/Podfile.lock'],
                        [scanPattern: '**/*.js'],
                        [scanPattern: '**/pom.xml'],
                        [scanPattern: '**/package-lock.json']
                    ],
                    unstableBuildOnScanningWarnings: false
                )
            }
        }
    }
}

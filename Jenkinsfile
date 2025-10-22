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
                        [scanPattern: '**/*.tar.gz'], // targz (default)
                        [scanPattern: '**/*.zip'],    // zip (default)
                        [scanPattern: '**/*.jar'],    // Java (default)
                        [scanPattern: '**/*.ear'],    // Java (default)
                        [scanPattern: '**/*.war'],    // Java (default)
                        [scanPattern: '**/Podfile.lock'], // iOS
                        [scanPattern: '**/*.js']      // JavaScript
                    ],
                    reachability: [
                        failOnError: false,
                        java: [options: [], properties: [], tool: ''],
                        javaAnalysis: [
                            algorithm: 'RTA_PLUS',
                            enable: false,
                            entrypointStrategy: 'ACCESSIBLE_CONCRETE',
                            force: false
                        ],
                        jsAnalysis: [enable: false, force: false, sourceFiles: [[pattern: '']]]
                    ],
                    unstableBuildOnScanningWarnings: false
                )
            }
        }
    }
}

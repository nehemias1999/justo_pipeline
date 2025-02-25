pipeline {

    agent any

    environment {

        // Ajustar estas rutas según tu instalación
        GenexusPath = "C:\\Program Files (x86)\\GeneXus\\GeneXus18U9"
        MSBuildEXEPath = "C:\\Program Files (x86)\\Microsoft Visual Studio\\2019\\BuildTools\\MSBuild\\Current\\Bin\\amd64\\MSBuild.exe"
        ServerUsername = 'sa_jenkins_genexus'
        ServerPassword = '567NTb0L4L4wjK4hZkAl'
        WorkingDirectory = "C:\\Models\\Estimaciones"
        DbaseServerUsername = 'root'
        DbaseServerPassword = 'root'

        updateScript = '"%MSBuildEXEPath%" "%GenexusPath%\\TeamDev.msbuild" ' +
                       '/p:DbaseServerUsername=%ServerUserName% ' +
                       '/p:DbaseServerPassword=%ServerPassword% ' +
                       '/p:WorkingDirectory="%WorkingDirectory%" ' + 
                       '/p:ServerUserName=%ServerUserName% ' +
                       '/p:ServerPassword=%ServerPassword% ' +
                       '/t:update' 

    }

    stages {
        
        stage('Update KB') {

            steps {

                script {

                    bat label: 'Update Script',
                    script: "${env.updateScript}"

                }
                
            }

        }
        
        // stage('Build Solution') {
 
        //     steps {
 
        //         bat """
        //             "\"${MSBUILD_PATH}\"" "${KB_PATH}\\Generated\\tu_solucion.sln" \
        //             /t:Rebuild \
        //             /p:Configuration=${params.BUILD_CONFIG} \
        //             /p:Platform="Any CPU" \
        //             /p:DeployOnBuild=true \
        //             /p:PublishProfile=Local
        //         """
 
        //     }
 
        // }
 
    }

}

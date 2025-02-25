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

    }

    stages {
        
        stage('Update KB') {

            steps {

                script {

                    bat label: 'Update Script',
                    script: '"${env.MSBuildEXEPath}" "${env.GenexusPath}\\TeamDev.msbuild" /p:DbaseServerUsername='${env.ServerUserName}' /p:DbaseServerPassword='${env.ServerPassword}' /p:WorkingDirectory="${env.WorkingDirectory}" /p:ServerUserName='${env.ServerUsername}' /p:ServerPassword='${env.ServerPassword}' /t:update'

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

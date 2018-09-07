try{
    node {
    echo 'Build Started'
    stage('Checkout'){
         git branch: 'master', credentialsId: 'bitbucket', url: 'https://github.com/devopstrainingblr/Ant-WebProject.git'
    }
        stage('build'){
        bat 'ant -f build-mt.xml'
    }
        /*stage('build'){
        sh 'ant -f build-mt.xml'
    }*/
    
    stage('Email'){
     body_msg = ''' Jenkins Job success 
   
    '''+"$JOB_URL"+''' 
    Thanks
    Jenkins
    '''
   mail bcc: '', body: body_msg, cc: '', from: '', replyTo: '', subject: 'Job Success', to: 'devopstraining@gmail.com'
   
    }
  }
}catch(error){
   echo 'Some error occured, Please verify' 
   throw error
}

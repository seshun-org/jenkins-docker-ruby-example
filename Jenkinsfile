node {
    
  stage 'Checkout'

  git 'https://github.com/Cox-Automotive/jenkins-docker-ruby-example.git'
        
  stage 'Package Docker image'

  def img = docker.build('coxauto/jenkins-docker-ruby-example:latest', '.')

  stage 'Publish'
  docker.withRegistry('https://nexus.coxautodev.com', 'nexus-admin') {
     img.push('latest')
  }

}

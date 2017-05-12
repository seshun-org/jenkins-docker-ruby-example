node('dind') {
    
  stage 'Checkout'

  git 'https://github.com/Cox-Automotive/jenkins-docker-ruby-example.git'
        
  stage 'Package Docker image'

  def img = docker.build('seshun/ruby-sample:latest', '.')

  stage 'Publish'
  docker.withRegistry('https://index.docker.io/v1/', 'seshun') {
     img.push('latest')
  }

}

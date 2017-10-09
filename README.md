# armgen-travis-config

Para configurar o projeto para utilizar a conf:

	before_install:
	- "git clone https://github.com/armgen/armgen-travis-config.git"
	- "cd armgen-travis-config && sh install-custom-repo.sh"

Para adicionar as chaves de segurança:

	travis encrypt CI_DEPLOY_USERNAME=admin --add env.global
	travis encrypt CI_DEPLOY_PASSWORD=@amz.ARM --add env.global

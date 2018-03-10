# armgen-travis-config

Para configurar o projeto para utilizar a conf:

	before_install:
	- "git clone https://github.com/armgen/armgen-travis-config.git"
	- "cd armgen-travis-config && sh install-custom-repo.sh"

Para adicionar as chaves de segurança:

	travis encrypt REPO_SERVER_PASSWORD=admin --add env.global
	travis encrypt REPO_SERVER_USER=@amz.ARM --add env.global

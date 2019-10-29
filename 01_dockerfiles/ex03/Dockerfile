FROM	ubuntu:latest

RUN 	apt-get update &&\
			apt-get install -y curl openssh-server ca-certificates runit &&\
			curl https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh | bash &&\
			EXTERNAL_URL="http://gitlab.example.com" apt-get -y install gitlab-ce

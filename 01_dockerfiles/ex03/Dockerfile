FROM	debian

ENV			TERM=xterm

RUN		 	apt-get update &&\
			apt-get install -y xterm curl openssh-server ca-certificates postfix &&\
			curl -s https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh | bash &&\
			apt-get install -y gitlab-ce &&\
			sed -i "s/# grafana\['enable'\] = true/grafana['enable'] = false/g" /etc/gitlab/gitlab.rb &&\
			sed -i "s/unicorn\['worker_timeout'\] = 60/unicorn\['worker_timeout'\] = 300/g" /etc/gitlab/gitlab.rb
			# sed -i "s/# letsencrypt\['enable'\] = nil/letsencrypt\['enable'\] = true/g" /etc/gitlab/gitlab.rb &&\
			# sed -i "s/external_url 'http://gitlab.example.com'/external_url 'https://localhost'/g" /etc/gitlab/gitlab.rb

EXPOSE		22 80 443

ENTRYPOINT	(/opt/gitlab/embedded/bin/runsvdir-start &) && \
			gitlab-ctl reconfigure &&\
			tail -f /dev/null


# docker build -t ex03 .
# docker run -it --shm-size=4g --restart=on-failure -p 8080:80 -p 8022:22 -p 8443:443 --privileged ex03
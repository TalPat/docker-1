# name ft-rails
FROM						ruby:latest

RUN							gem install rails sqlite3 &&\
								apt update &&\
								apt install nodejs -y

ONBUILD ADD			app /opt/app

ONBUILD WORKDIR	/opt/app

ONBUILD EXPOSE	3000

ONBUILD RUN			bundle install &&\
								bundle exec rake db:migrate &&\
								bundle exec rake db:seed

#sample app:
# git clone https://bitbucket.org/railstutorial/sample_app_4th_ed.git

# docker build . -t ft-rails:on-build

# FROM		ft-rails:on-build
# EXPOSE	3000
# CMD			["rails", "s", "-b", "0.0.0.0", "-p", "3000"]

# docker build . -t example
# docker run -it -p 3000:3000 example
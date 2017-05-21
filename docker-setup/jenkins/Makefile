VENDOR = he14vis
NAME = jenkins
VERSION = 1.0
JENKINS_HOME = /home/ubuntuserver/jenkins
JENKINS_PORT = 8080

default: run

run: build
	docker run -d \
	 --name $(VENDOR)-$(NAME) \
	 -p $(JENKINS_PORT):8080 \
	 -v $(JENKINS_HOME):/var/jenkins_home \
	 -v /var/run/docker.sock:/var/run/docker.sock \
	 -v /usr/bin/docker:/usr/bin/docker \
	 -t $(VENDOR)/$(NAME):$(VERSION)

build: Dockerfile
	docker build -t $(VENDOR)/$(NAME):$(VERSION) --rm .

stop:
	docker stop $(VENDOR)-$(NAME)

remove:
	docker rm $(VENDOR)-$(NAME)


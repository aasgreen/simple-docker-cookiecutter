#TAG    			:= $$(git describe --tags)
TAG 			:= latest	
#REGISTRY		:= registry-1.docker.io
USER 			:= aasgreen
PROJECT			:= {{cookiecutter.project_name}}
#REGISTRY_NAME	:= ${REGISTRY}/${PROJECT}/${IMG}

IMG_WEB_SVC    		:= ${USER}/${PROJECT}:${TAG}
IMG_WEB_SVC_JYP    		:= ${USER}/${PROJECT_JYP}:${TAG}
#REGISTRY_WEB_SVC	:= ${REGISTRY}/${PROJECT}/${NAME_WEB_SVC}:${TAG}
.PHONY:

test:
	echo ${IMG_WEB_SVC}
	echo ${TAG}
	echo ${PROJECT}
	echo ${PROJECT}:${TAG}

build_docker: 
	docker build -t ${IMG_WEB_SVC} ./docker
	

run_docker:
	docker run --shm-size=1g --ulimit memlock=-1 --ulimit stack=67108864 --memory-swap -1 -it -v ${PWD}:/work/ -p 8001:8000 ${IMG_WEB_SVC}

clean: 
	find -name "*~" -delete
	-rm .python_history
	-rm -rf .config
	-rm -rf .cache

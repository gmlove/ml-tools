
BUILD_DIR=build
TF_DOCKER_HOME=../tensorflow/tensorflow/tools/docker/
DOCKER_FILE=
IMAGE_NAME=
VERSION=

clean:
	rm -rf ${BUILD_DIR}

build: clean
	mkdir -pv ${BUILD_DIR}
	cp -rf ${TF_DOCKER_HOME}/* ${BUILD_DIR}/
	cp ${DOCKER_FILE} ${BUILD_DIR}/
	cd ${BUILD_DIR} && docker build -t ${IMAGE_NAME}:${VERSION} -f ${DOCKER_FILE} .

gpu-py3:
	version=$$(cat Dockerfile.gpu.py3 | grep TENSORFLOW_VERSION | grep ENV | cut -d' ' -f3) && \
	make build DOCKER_FILE=Dockerfile.gpu.py3 IMAGE_NAME=twaiclub/tensorflow-gpu-python3 VERSION=$$version

py3:
	version=$$(cat Dockerfile.py3 | grep TENSORFLOW_VERSION | grep ENV | cut -d' ' -f3) && \
	make build DOCKER_FILE=Dockerfile.py3 IMAGE_NAME=twaiclub/tensorflow-python3 VERSION=$$version


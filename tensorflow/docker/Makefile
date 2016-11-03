
BUILD_DIR=build
TF_DOCKER_HOME=../tensorflow/tensorflow/tools/docker/

gpu-py3:
	mkdir -pv ${BUILD_DIR}
	cp -rf ${TF_DOCKER_HOME}/* ${BUILD_DIR}/
	cp Dockerfile.gpu.py3 ${BUILD_DIR}/
	cd ${BUILD_DIR} && docker build -t twaiclub/tensorflow-gpu-python3:0.11.0rc2 -f Dockerfile.gpu.py3 .




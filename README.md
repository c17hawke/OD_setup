# Commands

## download gitignore using curl

```bash
curl https://raw.githubusercontent.com/c17hawke/general_template/main/.gitignore > .gitignore
```
## download init_setup.sh using curl

```bash
curl https://raw.githubusercontent.com/c17hawke/general_template/main/init_setup.sh > init_setup.sh
```
## tensorflow verification

```bash
python -c "import tensorflow as tf;print(tf.config.list_physical_devices('GPU'))"
```
# Installation of Object Detection API


## create a TensorFlow directory 
```bash
mkdir TensorFlow && cd TensorFlow
```
## Clone the TensorFlow models folder here

```bash
git clone https://github.com/tensorflow/models.git
```
remove .git directory of models repository to avoid git conflicts

add models folder to .gitignore
```bash
echo "TensorFlow/models" >> .gitignore
```

## Protobuff Installation/Compilation

- Visit the link - https://github.com/protocolbuffers/protobuf/releases
    - windows user -
        search for -  protoc-3.20.1-win64.zip
    - for mac users -
        search for -  protoc-3.20.1-osx-x86_64.zip
    - for linux users -
        ```
        sudo apt install -y protobuf-compiler
        ```
- Unzip into root folder and add `<PATH TO protoc folder>/bin` into sytstem environment variable

- run the following command:
```bash
cd TensorFlow/models/research
protoc object_detection/protos/*.proto --python_out=.
```

## Install COCO API

```bash
pip install git+https://github.com/philferriere/cocoapi.git#subdirectory=PythonAPI
```

## Install Object Detection API

```bash
cp object_detection/packages/tf2/setup.py .
python -m pip install .
```

## test yout intallation -
```bash
python object_detection/builders/model_builder_tf2_test.py
```

# Run examples -

- Create workspace/example_1 directory in project root
    ```bash
    mkdir -p workspace/example_1
    ```

- cd to workspace/example_1
    ```bash
    cd workspace/example_1
    ```
- Download notebook
    ```bash
    curl https://tensorflow-object-detection-api-tutorial.readthedocs.io/en/2.2.0/_downloads/7f6123c070712ed53dd2521219dd011c/plot_object_detection_simple.ipynb > plot_object_detection_simple.ipynb
    ```

# Custom model traning
```bash
mkdir workspace/training_demo
cd workspace/training_demo
mkdir -p annotations exported-models models pre-trained-models images/test images/train
```

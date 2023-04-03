# Commands

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

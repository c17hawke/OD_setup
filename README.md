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
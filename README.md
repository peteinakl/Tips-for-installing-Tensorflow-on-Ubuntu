Setting up tensorflow on Ubuntu is pretty straight forward, however there are a couple of gotchas.

There's a great (official) install guide here: https://www.tensorflow.org/install/install_linux

I like native, so for Python 3.x the crib sheet is:
sudo apt-get update
sudo apt-get install python3-pip python3-dev python3-pip
pip3 install tensorflow     # Python 3.n; CPU support (no GPU support)
pip3 install tensorflow-gpu # Python 3.n; GPU support <- I dont have a decent GPU, so unused for me

There's also a trick with mock. You'll want to:
sudo pip3 uninstall mock
sudo pip3 install mock
If you don't do this, sometimes you'll find mock throws error when importing TensorFlow.
 
Then test Tensorflow:
python3
# Python
import tensorflow as tf
hello = tf.constant('Hello, TensorFlow!')
sess = tf.Session()
print(sess.run(hello))

Now you should get:
Hello, TensorFlow!

If you plan on using the example modules and code, you also need two more things - this is the part they don't seem to cover in the docs. You need to also add:
pip install ipykernel
pip install tensorflow_hub

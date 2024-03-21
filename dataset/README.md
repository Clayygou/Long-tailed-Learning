# Download the CIFAR-100 dataset.

wget https://www.cs.toronto.edu/~kriz/cifar-100-python.tar.gz

tar -xzf cifar-100-python.tar.gz

mv cifar-100-python ./datasets/

rm cifar-100-python.tar.gz


# Download the CIFAR-10 dataset.

wget https://www.cs.toronto.edu/~kriz/cifar-10-python.tar.gz

tar -xzf cifar-10-python.tar.gz

mv cifar-10-batches-py ./datasets/

rm cifar-10-python.tar.gz

Sonnet 库使用面向对象的方法，允许创建定义一些前向传导计算的模块。模块用一些输入 Tensor 调用，添加操作到图里并返回输出 Tensor。其中一种设计选择是通过在随后调用相同的模块时自动重用变量来确保变量分享被透明化处理。 该库兼容 Linux/Mac OS X 和 Python 2.7。TensorFlow 的版本必须至少为 1.0.1。Sonnet 支持 TensorFlow 的 virtualenv 安装模式，以及 nativ pip 安装

# ![Sonnet](images/sonnet_logo.png)

Sonnet is a library built on top of TensorFlow for building complex neural
networks.


## Installation

Sonnet can be installed from pip, with or without GPU support.

This installation is compatible with Linux/Mac OS X and Python 2.7 and
3.{4,5,6}. The version of TensorFlow installed must be at least 1.2. Installing
Sonnet supports the [virtualenv installation mode](https://www.tensorflow.org/install/install_linux#installing_with_virtualenv)
of TensorFlow, as well as the [native pip install](https://www.tensorflow.org/install/install_linux#installing_with_native_pip).

To install sonnet, run:

```shell
$ pip install dm-sonnet
```

Sonnet will work with both the CPU and GPU version of tensorflow, but to allow
for that it does not list Tensorflow as a requirement, so you need to install
Tensorflow separately if you haven't already done so.

## Usage Example

The following code constructs a Linear module and connects it to multiple
inputs. The variables (i.e., the weights and biases of the linear
transformation) are automatically shared.

```python
import sonnet as snt

# Provide your own functions to generate data Tensors.
train_data = get_training_data()
test_data = get_test_data()

# Construct the module, providing any configuration necessary.
linear_regression_module = snt.Linear(output_size=FLAGS.output_size)

# Connect the module to some inputs, any number of times.
train_predictions = linear_regression_module(train_data)
test_predictions = linear_regression_module(test_data)
```

# Documentation

Check out the full documentation page
[here](https://deepmind.github.io/sonnet/).

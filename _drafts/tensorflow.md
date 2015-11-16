---
layout: post
title: TensorFlow install on MacOSX
---

[TensorFlow](https://github.com/tensorflow/tensorflow)는 구글에서 제작한 머신러닝 라이브러리임.

Mac OS X El capitan 에서 설치시 오류가 발생함.
1)시스템 보호 영역에서 six 를 설치할 수 없다는 오류 발생.
2)pip --ignore-installed six 로 설치 오류는 피할 수 있지만, copyreg 관련 오류 발생.

결국 docker를 실행하여 Ubuntu에 설치하여 Hello world를 실행함.
```
kkr@a0e0f417d94b:~/workspace/tensorflow$ python
Python 2.7.6 (default, Jun 22 2015, 17:58:13)
[GCC 4.8.2] on linux2
Type "help", "copyright", "credits" or "license" for more information.
>>> import tensorflow as tf
>>> hello = tf.constant('Hello, TensorFlow!')
>>> sess = tf.Session()
I tensorflow/core/common_runtime/local_device.cc:25] Local device intra op parallelism threads: 1
I tensorflow/core/common_runtime/local_session.cc:45] Local session inter op parallelism threads: 1
>>> print sess.run(hello)
Hello, TensorFlow!
>>> a = tf.constant(10)
>>> b = tf.constant(32)
>>> print sess.run(a+b)
42
```

샘플 디렉토리에 안드로이드 예제가 있으므로 분석할 계획임.


Ansible Role: Caffe
=========

[![Build Status](https://travis-ci.org/djx339/ansible-role-caffe.svg?branch=master)](https://travis-ci.org/djx339/ansible-role-caffe)

Install [Caffe](http://caffe.berkeleyvision.org/), a deep learning framework by the BVLC, on Ubuntu/CentOS.

Requirements
------------

Please visit [Caffe Requirements](http://caffe.berkeleyvision.org/installation.html#prerequisites)

Role Variables
--------------

`caffe_repo`: The git repo of caffe. (default: https://github.com/BVLC/caffe.git)

`caffe_root`: The path to store caffe code on remote server. (default: /opt/caffe)

`caffe_version`: The caffe version. It can be git branch, git tag, string `HEAD` and SHA-1 hash. (default: HEAD)

`caffe_with_virtualenv`: Install caffe python dependence to isolated python environment. (default: True)

`caffe_virtualenv`: The isolated python environment path on remote server. (default: "/opt/pyenv/caffe")

`caffe_use_cudnn`: Building Caffe with cudnn. (default: False)

`caffe_cpu_only`: Building Caffe only support CPU. (default: True)

`caffe_opencv_versioin`: The OpenCV version. (default: 2)

`caffe_blas`: The BLAS choice. `atlas` for ATLAS, `mkl` for MKL, `open` for OpenBlas. (default: atlas)

`caffe_matlab_dir`: The MATLAB dir. (default: "")

`caffe_with_python_layer`: Building caffe with python layer. (default: True)

`caffe_use_pkg_config`: Using `pkg-config` to specify OpenCV library paths. (default: True)

Dependencies
------------

None.

Example Playbook
----------------

```yaml
- hosts: all
  become: yes

  roles:
    - { role: djx339.ansible-role-cuda }
```

Only install dependence:

    ansible-playbook -i inventory playbook-caffe.yml --tags "dep"

Skip download models:

    ansible-playbook -i inventory playbook-caffe.yml --skip-tags "model"

Only download models:

    ansible-playbook -i inventory playbook-caffe.yml --tags "src,model"

License
-------

BSD

Author Information
------------------

This role was created by [Daniel D](https://github.com/djx339).

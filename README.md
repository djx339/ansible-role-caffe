Ansible Role: [Caffe](http://caffe.berkeleyvision.org/)
=========

Ansible Role for [Caffe](http://caffe.berkeleyvision.org/), a deep learning framework by the BVLC, on Ubuntu.

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

`caffe_cpu_only`: Building Caffe only support CPU. (default: False)

`caffe_opencv_versioin`: The OpenCV version. (default: 3)

`caffe_blas`: The BLAS choice. `atlas` for ATLAS, `mkl` for MKL, `open` for OpenBlas. (default: atlas)

`caffe_matlab_dir`: The MATLAB dir.

`caffe_with_python_layer`: Building caffe with python layer. (default: True)

`caffe_use_pkg_config`: Using `pkg-config` to specify OpenCV library paths. (default: False)

Dependencies
------------

None.

Installing
----------

This role is only avaiable on github. You can install it by create a `roles.yml` file and install it by `ansible-galaxy install -r roles.yml`

The jq role section of the content of the roles.yml

```yaml
# caffe
- src: https://github.com/djx339/ansible-role-caffe
  name: caffe
```

Example Playbook
----------------

```yaml
- hosts: all
  become: yes

  roles:
    - { role: caffe }
```

Only install dependence:

    ansible-playbook -i inventory playbook-caffe.yml --tags "dep"

Skip download models:

    ansible-playbook -i inventory playbook-caffe.yml --skip-tags "model"

License
-------

BSD

Author Information
------------------

This role was created by [Daniel D](https://github.com/djx339).

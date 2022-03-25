# pylearn2_python3

Pylearn2 for python3.8

#Software required

- Cuda toolkit
- Visual studio
- Anaconda
- Cuda-supported GPU

#Do changes

- command to run in windows `set THEANO_FLAGS=mode=FAST_RUN,device=gpu,floatX=float32 && python pylearn2\scripts\train.py pylearn\scripts\cifar10_convolutional.yaml`

- `conda install theano pygpu`
- `conda install cython`
- `conda install nvidia cudnn`

#Lib site-packages changes

#Theano package changes

- file `theano\sandbox\cuda\nvcc_compiler.py`
- change -> `ver_line = decode(p_out[0]).strip().split('\n')[-2]` this is for cuda version error
- file `theano\sandbox\cuda\cuda_ndarray.cu` for mod.cu error
- change -> `const char * clipmode = PyString_AsString(clipmode_obj)` `const char * cstr = PyString_AsString(str)`
- file `pylearn2\packaged_dependenciestheano_linear\unshared_conv\localdot.py` remove `import gpu_unshared_conv 

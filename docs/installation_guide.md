# Installation Guide

## Requirements

HiEval leverage the [Integer Set Library](http://isl.gforge.inria.fr/) and the [Barvinok Library](http://barvinok.gforge.inria.fr/) to perform metrics analysis. 

## Install Steps
We recommend installing HiEval on a virtual python environment to avoid python library conflicts.

1. Build a virtual python environment
```
$ conda create -n HiEval_env python=3.8
```
It will create a "HiEval_env" directory. You can use your favorite directory name.

3. Activate the virtual environment
```
$ conda activate HiEval_env
```
If you want to exit this environment, just execute ``conda deactivate`` command.

4. Install Python Libraries
HiEval requires the following python library.

 ```
(HiEval_env) $ git clone https://github.com/ZhuangzhuangWu/HiEval.git
(HiEval_env) $ cd HiEval
(HiEval_env) $ pip install -r ./requirements.txt
(HiEval_env) $ ./init.sh
```

5. Set environment variable 
${project_path} is the installation directory for libraries.

```
export LD_LIBRARY_PATH=${project_path}/lib:$LD_LIBRARY_PATH
export LD_LIBRARY_PATH=${project_path}/cJson/usr/lib/x86_64-linux-gnu/:$LD_LIBRARY_PATH
```

6. Build a tool named 'scop' to perform static analysis on C kernels.
```
cd scop
make 
```
![image](https://github.com/ZhuangzhuangWu/HiEval/assets/60685759/5b406259-09ff-4c1c-a7e2-bfa0aac66887)# HiEval
NOTE: Currently, we are restructuring and refactoring codes. Please stay tuned for the updated version!
We offer a Docker image that contains all the necessary dependencies and source codes.
To start with HiEval, get the docker image and run a container using the image.
'''
  $ sudo docker pull registry.cn-hangzhou.aliyuncs.com/mprl/hieval:v0.2
  $ sudo docker run -tid --name=HiEval registry.cn-hangzhou.aliyuncs.com/mprl/hieval:v0.2 /bin/bash
  $ docker attach HiEval
'''

 For example, you can run a simple case with the following command:
'''
 (base) $ conda activate HiEval_env
 (HiEval_env) $ cd /root/HiEval
 (HiEval_env) $ python HiEval.py --arch './data/arch/os_systolic.json’		\
					    --mapping './data/mapping/gemm_256_os.json’	\ 
					    --csv_name "gemm_256_os.csv"
'''

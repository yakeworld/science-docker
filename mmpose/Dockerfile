FROM nvcr.io/nvidia/pytorch:22.03-py3
RUN pip config set global.index-url https://pypi.mirrors.ustc.edu.cn/simple/
RUN pip uninstall opencv-python  
RUN pip uninstall opencv-python-headless 
RUN pip install opencv-python==4.5.5.62  ##--proxy='socks5://172.18.0.12:1080'
RUN pip install opencv-python-headless==4.5.5.62 ##-i https://pypi.mirrors.ustc.edu.cn/simple/
RUN pip install -U openmim
RUN mim install mmcv-full

WORKDIR /workspace
RUN git clone https://github.com/open-mmlab/mmpose.git
RUN cd mmpose
RUN pip install -r requirements.txt  --proxy='socks5://172.18.0.12:1080'
RUN pip install -v -e .

WORKDIR /workspace
RUN git clone https://github.com/open-mmlab/mmtracking.git
RUN cd mmtracking
RUN pip install -v -e .

RUN pip install mmdet

## jupyter 支持主机端GUI
RUN apt-get install libx11-dev -y
RUN apt-get install libgl1 -y
RUN pip install vedo








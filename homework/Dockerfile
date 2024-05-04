FROM ultralytics/yolov5

WORKDIR /

RUN apt-get update -y && apt-get install unzip && apt-get install wget

COPY itri-bev.zip /

RUN unzip itri-bev.zip

RUN chmod +x itri-bev/detect.py

RUN pip install -r itri-bev/requirements.txt

RUN python itri-bev/detect.py --view-img --nosave --weights yolov5x.pt --source itri-bev/video/argoverse/argoverse.mp4  --run-liteMono --run-bev --classes 2 5 7

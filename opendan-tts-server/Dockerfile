FROM continuumio/miniconda3
RUN apt update && apt install espeak-ng ffmpeg -y
WORKDIR /root
ADD ./requirements.txt .
RUN pip config set global.index-url https://pypi.mirrors.ustc.edu.cn/simple/
RUN pip config set install.trusted-host pypi.mirrors.ustc.edu.cn
RUN pip install -r requirements.txt
ADD ./src .
RUN python -m nltk.downloader punkt
CMD ["python", "main.py"]

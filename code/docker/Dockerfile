FROM horovod/horovod:sha-9b42eda
LABEL description="DeepXDE with Tensorflow PyTorch and GPU support"

COPY requirements.txt /root
WORKDIR /root
RUN /usr/bin/python -m pip install --upgrade pip
RUN pip3 install -r requirements.txt 
RUN apt-get update && apt-get install -y --no-install-recommends imagemagick \
 && apt-get clean \
 && rm -rf /var/lib/apt/lists/*
EXPOSE 8888/tcp
ENV SHELL /bin/bash
ENTRYPOINT ["jupyter", "notebook", "--ip", "0.0.0.0", "--no-browser", "--allow-root"]

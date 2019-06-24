FROM amazonlinux:2
EXPOSE 8888
ADD requirements.txt /
RUN yum install -y -q wget && \
	wget -q -O /tmp/get-pip.py https://bootstrap.pypa.io/get-pip.py && \
    chmod a+x /tmp/get-pip.py && \
    /tmp/get-pip.py
RUN pip install  -r requirements.txt
ADD thumbor.conf /etc/thumbor.conf
ENTRYPOINT ["/usr/bin/thumbor", "--conf","/etc/thumbor.conf", "--log-level", "critical"]

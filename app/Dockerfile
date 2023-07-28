FROM amazon/aws-lambda-provided:al2

WORKDIR /home/app
ADD target/function.zip .

RUN yum install -y unzip && unzip function.zip

RUN cp /home/app/bootstrap /var/runtime/bootstrap
RUN cp /home/app/func /var/task/func

RUN chmod 755 /var/runtime/bootstrap
RUN chmod 755 /var/task/func

CMD ["com.github.lbovolini.handler.LambdaHandler"]

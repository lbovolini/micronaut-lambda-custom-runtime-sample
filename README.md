## How to build and run

```bash
cd app

mvn clean package -Dpackaging=docker-native -Dmicronaut.runtime=lambda -Pgraalvm

docker build -t micronaut-lambda-custom-runtime-sample .

docker run --rm -v ~/.aws-lambda-rie:/aws-lambda -p 9000:8080 \
micronaut-lambda-custom-runtime-sample:latest

curl -XPOST \ 
"http://localhost:9000/2015-03-31/functions/function/invocations" \
-d '{}'

```
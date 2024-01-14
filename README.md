# Rekognitor.Grpc.Protos

**Push image for running API from docker repository:**

    docker push vitor5166/detect.rekognitor.api:latest

**Run with client id and secret environment variables:**

    docker run -dt --env CLIENT_ID="YOUR_CLIENT_ID" --env SECRET="{YOU_SECRET}" -p 8080:8080 -p 443:443 -P --name detect.rekognitor.api detect.rekognitor.api:latest

**Retrieve proto files from this repository:** [https://github.com/vitao-coder/Rekognitor.Grpc.Protos](https://github.com/vitao-coder/Rekognitor.Grpc.Protos)
  
**Compile protos and consume in your application with a url that runs:** 

    vitor5166/detect.rekognitor.api.

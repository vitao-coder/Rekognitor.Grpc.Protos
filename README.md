**For use with CPU (Core processors)**
-

**Push image for running API from docker repository:**

    docker push vitor5166/detect.rekognitor.api:latest

**Run with client id and secret environment variables:**

    docker run -dt --env CLIENT_ID="YOUR_CLIENT_ID" --env SECRET="{YOU_SECRET}" -p 8080:8080 -p 443:443 -P --name detect.rekognitor.api detect.rekognitor.api:latest

**Retrieve proto files from this repository:** [https://github.com/vitao-coder/Rekognitor.Grpc.Protos](https://github.com/vitao-coder/Rekognitor.Grpc.Protos)
  
**Compile protos and consume in your application with a url that runs:** 

    vitor5166/detect.rekognitor.api.

For use with Streaming from RTSP to send to detect.rekognitor.api
-

**Push image for running Streamer from docker repository:**

    docker push vitor5166/rekognitor-streamer:latest

**Run with url for detect services (vitor5166/detect.rekognitor.api) with, port for streamer environment variables:**

    docker run -dt --env PORT="{port to run streamer. ex: 8080}" --env MODE={1=person, 2=knifesAndGuns 3=brazilianCarplates} --env DETECT_SERVICES_URL="{address to detect services}:{port to detect services}" -p 8080:8080 -p 1883:1883 -P --name rekognitor-streamer vitor5166/rekognitor-streamer:latest

**To connect on MQTT service in streamer to receive responses from detection:**

    host: mqtt://you_streamer_address_or_ip:1883
    No requires auth

**For use with GPU (CUDA drivers)** IN WIP - Not Functional
-
**Install CUDA drivers on virtualization service that you have:**
https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/latest/install-guide.html

**Test with a sample workload to guarantee nvidia drivers on virtualization platform:**
https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/latest/sample-workload.html

~~**Push image for running API from docker repository:**~~

    docker push vitor5166/detect.rekognitor.api.gpu:latest
  ~~**Run with client id and secret environment variables:**~~

    docker run -dt --runtime=nvidia --gpus all--env CLIENT_ID="YOUR_CLIENT_ID" --env SECRET="{YOU_SECRET}" -p 8080:8080 -p 443:443 -P --name detect.rekognitor.api.gpu detect.rekognitor.api.gpu:latest

~~**Retrieve proto files from this repository:** [https://github.com/vitao-coder/Rekognitor.Grpc.Protos]~~(https://github.com/vitao-coder/Rekognitor.Grpc.Protos)
  
~~**Compile protos and consume in your application with a url that runs:**~~ 

    vitor5166/detect.rekognitor.api.gpu

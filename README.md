## to build the docker container on linux 

sudo docker system prune -a

sudo docker build . -t aadharmaskinguat

sudo docker run -p 8080:8080 aadharmaskinguat

sudo docker tag aadharmaskinguat:latest aadharmaskinguat:latest

sudo docker push aadharmaskinguat:latest

---------------------------------------------------------------------

## to push the container to azure registry

``` export command ```

export ACR_REGISTRY=aadharmaskinguat.azurecr.io
export ACR_NAMESPACE=aadharmaskingapp1
export ACR_IMAGE_NAME=aadharmaskinguat
export ACR_IMAGE_TAG=latest
echo $ACR_REGISTRY, $ACR_NAMESPACE, $ACR_IMAGE_NAME, $ACR_IMAGE_TAG

sudo docker login $ACR_REGISTRY

sudo docker tag aadharmaskinguat:latest $ACR_REGISTRY/$ACR_NAMESPACE/$ACR_IMAGE_NAME:$ACR_IMAGE_TAG

sudo docker images aadharmaskinguat:latest

sudo docker images $ACR_REGISTRY/$ACR_NAMESPACE/$ACR_IMAGE_NAME:$ACR_IMAGE_TAG

sudo docker push $ACR_REGISTRY/$ACR_NAMESPACE/$ACR_IMAGE_NAME:$ACR_IMAGE_TAG

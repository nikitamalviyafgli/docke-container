# list docker image
docker images

# lastest build
sudo docker build -t docker-image-name .
# OR 
docker build  -t ImageName:TagName dir

# run docker image
docker run -p 8080:8080 docker-image-name

# delete all docker images
docker system prune -a


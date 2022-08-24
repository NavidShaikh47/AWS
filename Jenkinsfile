docker build -t fastapi-image .
    
aws ecr get-login-password --region ap-south-1 | docker login --username AWS --password-stdin 045996574415.dkr.ecr.ap-south-1.amazonaws.com

docker build -t fastapi-image .

docker tag fastapi-image:latest 045996574415.dkr.ecr.ap-south-1.amazonaws.com/newrepo:latest

docker push 045996574415.dkr.ecr.ap-south-1.amazonaws.com/newrepo:latest

docker run -p 80:80 -i fastapi-image

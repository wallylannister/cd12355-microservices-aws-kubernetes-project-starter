docker build --build-arg DB_USERNAME=tuong --build-arg DB_PASSWORD=123456 -t anal-test
docker run -e DB_USERNAME=tuong -e DB_PASSWORD=123456 -p 5153:5153 anal-test
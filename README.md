# Docker


1) create directory:- 
mkdir Docker
2) Added files :-
touch Dockerfile , touch index.html

3) nano Dockerfile:-

FROM nginx:latest   
COPY ./index.html /usr/share/nginx/html/index.html   
WORKDIR /usr/share/nginx/html   
RUN date +%x_%H:%M:%S:%N >> ./index.html   

4) nano index.html     

<!doctype html>
<html>
  <head>
  </head>
  <body>
    <h2>Welcome to the nginx page in a docker container !!!</h2>

    <p>Current Date and Time is: <span id='date-time'></span></p>

    <script>
        var dateAndTime = new Date();
        document.getElementById('date-time').innerHTML=dateAndTime.toLocaleString();
        </script>

    <p>This Nginx docker container has been created by Avinash khadgi..</p>
    
    
    </body>
</html>

5) docker build -t nginx-image .     

6) docker images     

7) docker run -d -p 8081:80 --name nginx_container nginx        







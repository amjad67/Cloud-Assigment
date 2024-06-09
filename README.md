# UrgentNews-With-Docker

## Running images
### Running using `docker run`
* To run database container, setup `.env_db` file then use the following command:
```
$ sudo docker run -d -p 3306:3306 --env-file .env_db --name mariadb-news-container amjadediaily/urgentnews-database
```
* Example of `env_db`
```
MYSQL_DATABASE=urgentNews
MYSQL_USER=amjadediaily
MYSQL_PASSWORD=12345
MYSQL_ROOT_PASSWORD=root
```


* To run backend container, setup `.env_backend` file then use the following command:
```
$ sudo docker run -d -p 5000:5000 --env-file .env_backend --name news-backend-container amjadediaily/urgentnews-backend
```
* Example of `env_backend`
```
DB_HOST=<host-ip>
DB_USER=amjadediaily
DB_PASS=12345
DB_NAME=urgentNews
DB_PORT=3306
```

* To run frontend container use the following command:
```
$ sudo docker run -d -p 80:80 -e HOST_IP=<host-ip> --name news-frontend-container amjadediaily/urgentnews-frontend
```

* Go to following url in your browser to see the result
```
http://localhost
```

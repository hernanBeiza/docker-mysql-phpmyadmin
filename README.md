# docker-mysql-phpmyadmin
 Uso de MySQL y PhpMyAdmin a través de Docker 

## Requerimientos

- Docker
- Imagen MySQL
- Imagen PHPMyAdmin

## MySQL

- Bajar imagen

````
docker pull mysql:8.0.1
````

- Iniciar contenedor

````
docker run --name my-own-mysql -e MYSQL_ROOT_PASSWORD=mypass123 -d  -p 3306:3306 mysql:8.0.1
````

- El servicio de MySQL quedará expuesto
  - Usuario: root
  - Contraseña: mypass123
  - Puerto 3306

## PhpMyAdmin

- Bajar imagen

`````
docker pull phpmyadmin/phpmyadmin:latest
`````

- Iniciar contenedor

````
docker run --name my-own-phpmyadmin -d --link my-own-mysql:db -p 8081:80 phpmyadmin/phpmyadmin
````

- El servicio PhpMYAdmin quedará expuesto en:
  - Url: localhost:8081
  - Usuario: root
  - Contraseña: mypass123


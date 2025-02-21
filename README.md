# Instrucciones

* Los archivos del Sitio Web van en [html](./apache-php/html/)
* La configuración de los vhosts va en [vhost](./apache-php/vhost/)

# Ejecución del Contenedor

* Detener el contenedor con los comandos: 
```bash
docker-compose down
```
* Compilar el contenedor con los comandos: 
```bash
docker-compose build
```
* Inicializar el contenedor con los comandos: 
```bash
docker-compose up -d
```

# Ejecución del Terminal del Contenedor MYSQL
Ejecución del Terminal del Contenedor
```bash
docker run -it mysql8 bash
```
Ejecución del Terminal MYSQL (Contraseña 'toor')
```bash
mysql -u root -p
```

# Acceso al PhpMyAdmin
Entrar al navegador al enlace [localhost:8080](http://localhost:8080)

# Acceso al Sitio Web
Entrar al navegador al enlace [localhost](http://localhost)
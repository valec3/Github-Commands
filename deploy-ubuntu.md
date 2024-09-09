
### 1. **Conéctate a tu Droplet**
Conéctate a tu servidor de Digital Ocean a través de SSH:

```bash
ssh root@your_server_ip
```

### 2. **Actualiza el sistema**
Es importante actualizar los paquetes antes de instalar cualquier software:

```bash
sudo apt update
sudo apt upgrade -y
```

### 3. **Instalar Apache**
Apache es el servidor web que servirá tu proyecto PHP.

```bash
sudo apt install apache2 -y
```

Verifica que Apache esté corriendo:

```bash
sudo systemctl status apache2
```

### 4. **Instalar MySQL**
MySQL será tu sistema de gestión de bases de datos:

```bash
sudo apt install mysql-server -y
```

Ejecuta el script de seguridad de MySQL:

```bash
sudo mysql_secure_installation
```

Sigue las instrucciones para establecer una contraseña y fortalecer la seguridad.

### 5. **Instalar PHP**
Instala PHP junto con las extensiones necesarias para que funcione con MySQL:

```bash
sudo apt install php libapache2-mod-php php-mysql -y
```

Puedes verificar la versión de PHP instalada:

```bash
php -v
```

### 6. **Configurar Apache para priorizar PHP**
Edita el archivo de configuración de Apache para que los archivos `.php` se carguen primero:

```bash
sudo nano /etc/apache2/mods-enabled/dir.conf
```

Cambia el orden de `index.php`:

```bash
<IfModule mod_dir.c>
    DirectoryIndex index.php index.html index.cgi index.pl index.xhtml index.htm
</IfModule>
```

Guarda el archivo (`Ctrl+O`) y cierra el editor (`Ctrl+X`).

### 7. **Reinicia Apache**
Después de cualquier cambio en la configuración de Apache, debes reiniciar el servicio:

```bash
sudo systemctl restart apache2
```

### 8. **Configurar MySQL**
Accede a la consola de MySQL para crear una base de datos y un usuario:

```bash
sudo mysql
```

Dentro de la consola de MySQL, ejecuta los siguientes comandos para crear una base de datos, un usuario y darle permisos:

```sql
CREATE DATABASE nombre_base_datos;
CREATE USER 'usuario'@'localhost' IDENTIFIED BY 'contraseña';
GRANT ALL PRIVILEGES ON nombre_base_datos.* TO 'usuario'@'localhost';
FLUSH PRIVILEGES;
EXIT;
```

### 9. **Configurar el Firewall**
Permite el tráfico en el puerto 80 (HTTP) y 443 (HTTPS) en el firewall de tu servidor:

```bash
sudo ufw allow in "Apache Full"
sudo ufw enable
```

### 10. **Desplegar el Proyecto PHP**
1. Sube tu proyecto PHP a la carpeta `/var/www/html/`. Puedes usar SFTP o `scp` para transferir archivos.
   
   Ejemplo con `scp`:
   ```bash
   scp -r /ruta/local/de/tu/proyecto root@your_server_ip:/var/www/html/
   ```

2. Asegúrate de que los archivos PHP tengan los permisos correctos:
   ```bash
   sudo chown -R www-data:www-data /var/www/html/
   ```

### 11. **Configurar Virtual Host (Opcional, para dominios)**
Si estás usando un dominio, puedes configurar un Virtual Host:

```bash
sudo nano /etc/apache2/sites-available/your_domain.conf
```

Añade el siguiente contenido:

```apache
<VirtualHost *:80>
    ServerAdmin admin@your_domain
    ServerName your_domain
    ServerAlias www.your_domain
    DocumentRoot /var/www/html/your_project

    <Directory /var/www/html/your_project>
        Options Indexes FollowSymLinks
        AllowOverride All
        Require all granted
    </Directory>

    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
```

Habilita el Virtual Host:

```bash
sudo a2ensite your_domain.conf
sudo systemctl restart apache2
```

### 12. **Verificar la Instalación**
Abre tu navegador y accede a `http://your_server_ip` o tu dominio configurado. Si todo está bien, verás tu proyecto PHP ejecutándose.

### 13. **Instalar phpMyAdmin (Opcional)**
Para gestionar MySQL desde una interfaz gráfica, puedes instalar **phpMyAdmin**:

```bash
sudo apt install phpmyadmin php-mbstring php-zip php-gd php-json php-curl
```

Luego selecciona **Apache** cuando se te pida y configura **phpMyAdmin** siguiendo los pasos en pantalla.

### 14. **Seguridad Adicional (Opcional)**
- **HTTPS con Let’s Encrypt**:
   Si tienes un dominio, puedes agregar un certificado SSL gratuito con Let’s Encrypt:
   ```bash
   sudo apt install certbot python3-certbot-apache
   sudo certbot --apache
   ```

- **Desactivar el acceso a `phpMyAdmin` desde direcciones IP no seguras**:
   Edita el archivo de configuración de phpMyAdmin:
   ```bash
   sudo nano /etc/apache2/conf-available/phpmyadmin.conf
   ```

   Añade restricciones por IP.

---

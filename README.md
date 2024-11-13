manual como poner el OwnCloud en linux

1 abre tu historial

2.busca portugal

3. abre linux

4.abre terminal

5.pon esto en tu terminal

![Captura desde 2024-10-30 12-37-24](https://github.com/user-attachments/assets/87c3321c-8ad8-4f46-be68-b37e6c7ade41)
(![Captura desde 2024-10-30 12-37-37](https://github.com/user-attachments/assets/dcabf4f2-2287-4c88-a1fc-c21e8d48ae2a)

si te sale error es por que ya lo tiene

6.esperar tardara 6min

7.pon el siguiente paso

[![Captura desde 2024-10-30 13-06-37](https://github.com/user-attachments/assets/aad9c972-7e9f-4473-9787-9f166369bdca)

![Captura desde 2024-10-30 13-06-49](https://github.com/user-attachments/assets/85f96f5a-6cd8-4acf-adb7-9dd27e61ed20)

![Captura desde 2024-10-30 13-07-04](https://github.com/user-attachments/assets/43d24e89-abd8-4309-a16e-57628818d6b5)

![Captura desde 2024-10-30 13-07-27](https://github.com/user-attachments/assets/5d0019c4-930d-4dd6-8caa-78a8c794f853)

![Captura desde 2024-10-30 13-07-52](https://github.com/user-attachments/assets/6e445810-4768-479c-9f2d-dccf0c56739a)

a continuacion tienes que poner esto en la terminal

```console
CREATE DATABASE bbdd;
```

```console
CREATE USER 'usuario'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';
```

```console
GRANT ALL ON bbdd.* to 'usuario'@'localhost';
```
este comando es para salir del terminal de mysql
```console
exit
```

esto lo que hace es entrar a otra terminal i crear tu cuenta de localhost y de owncloud
si te sale error por que ya lo tienes

con estos comandos te extraen el archivo zip del owncloud 
ahora tienes que poner esto en tu terminal
```console
sudo cp ~/Bajadas/app-web.zip /var/www/html
```
Vaya al directorio `/var/www/html`
```console
cd /var/www/html
````
Descomprima el archivo que ha descargado
```console
sudo unzip app-web.zip
````
Copie los archivos en la carpeta `/var/www/html`, modifique `app-web` por el nombre del directorio donde se ha descomprimido su archivo.
```console
sudo cp -R app-web/. /var/www/html
````
Eliminamos la carpeta creada cuando hemos hecho un `zip`
```console
sudo rm -rf app-web/
````

## Eliminamos el archivo `index.html` de `apache2`
```console
sudo rm -rf /var/www/html/index.html
````


## Aplicación de permisos en nuestras aplicaciones web
Una vez descomprimidos los archivos de la aplicación web en el directorio `/var/www/html`, aplicamos los siguientes permisos en el directorio `/var/www/html`

```console
cd /var/www/html
````
```console
sudo chmod-R 775 .
````
```console
sudo chown -R usuario:www-data .
````

si te sale error en el owncloud coge todo lo metetes a la papelera i refrescas la pantalla y cuando salga archivo no encontrado lo vuelves a poner todo i se arreglara

<h1>Configuraciones básicas y creación de Dockers de prueba</h1>

<h2>Primer paso</h2>

Se debe construir un docker personalizado que incluya servidor openssh

Con el Dockerfile se contruira la imagen de los Dockers

Se usa el siguiente comando por consola:

<pre>
<code>  Docker build -t server:16.04 .
</code>
</pre>

<h2>Segundo paso, Despliegue</h2>

Se crean unas maquinas para el despliegue, en este caso se creará un servidor apache

Para ello usamos el siguiente comando:

docker run -d -P --name munin_node_web_server -p 2221:22 -p 80:80 server:16.04

docker run -d -P --name munin_master_web_server -p 2222:22 -p 8000:80 server:16.04

<h2>Tercer paso configurar alias</h2>

Primero: edita el archivo /etc/hosts y adiciona 2 alias a localhost

127.0.0.1 munin_node_web_server munin_master_web_server

Segundo: adición automática en el archivo de hosts del sistema

Usamos el siguiente comando en nuestra consola:

echo "127.0.0.1 munin_node_web_server munin_master_web_server" | sudo tee -a /etc/hosts

<h2>Cuarto paso confirmacion</h2>

Realizar prueba de conexion a la maquina creada anteriormente

ssh -o StrictHostKeyChecking=no root@munin_node_web_server -p 2221 -i key.private hostname
ssh -o StrictHostKeyChecking=no root@munin_master_web_server -p 2222 -i key.private hostname

Si la conexion se establece esta listo y se puede entrar a la configuración de Ansible.

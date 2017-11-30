<h1>Configuración de Ansible</h1>

<p>Se Instalan y se configuran los siguientes servicios :</p>

<li>Apache</li>
<li>Munin</li>

<h2>El primer paso es el siguiente :</h2>

Se utiliza el siguiente comando para instalar el servidor Web.

ansible-playbook -i hosts apache.yml

<h3>Segundo paso Instalar Munin</h3>

Para instalar munin el el servidor munin_node_web_server

se debe utilizar el siguiente comando :

ansible-playbook -i hosts munin_node.yml

Para instalar munin el el servidor munin_master_web_server

se debe utilizar el siguiente comando :

ansible-playbook -i hosts munin.yml
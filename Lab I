PRÁCTICAS DE LINUX – DOCUMENTACIÓN
🔹 PRÁCTICA 1: Instalación del Sistema Operativo (Linux)
📌 Pasos realizados
Se creó una máquina virtual en VirtualBox / VMware.
Se asignaron recursos mínimos:
RAM: 2 GB o más
CPU: 1–2 núcleos
Disco: 20 GB
Se configuró la red en modo Bridge.
Se montó la ISO del sistema operativo (ej: Ubuntu).
Se ejecutó la instalación siguiendo el asistente.
📌 Modo Bridge

Permite que la máquina virtual tenga una IP dentro de la misma red que el host, como si fuera otra computadora real.

🔹 PRÁCTICA 2: Configuración de red
📌 1. Configuración con DHCP
sudo dhclient

👉 Solicita automáticamente una IP al servidor DHCP.

📌 2. Configuración IP estática (temporal)
sudo ip addr add 192.168.1.100/24 dev eth0
sudo ip route add default via 192.168.1.1

👉 Asigna IP manual y puerta de enlace.

📌 3. Configuración permanente (Netplan - Ubuntu)
sudo nano /etc/netplan/01-netcfg.yaml

Ejemplo:

network:
  version: 2
  ethernets:
    eth0:
      dhcp4: no
      addresses: [192.168.1.100/24]
      gateway4: 192.168.1.1
      nameservers:
        addresses: [8.8.8.8, 8.8.4.4]

Aplicar cambios:

sudo netplan apply
📌 DNS de Google
nameserver 8.8.8.8
nameserver 8.8.4.4

👉 Permiten resolver nombres de dominio.

🔹 PRÁCTICA 3: Usuarios y Grupos
📌 Crear usuario
sudo adduser tu_nombre
📌 Agregar a sudoers
sudo usermod -aG sudo tu_nombre

👉 Le da permisos administrativos.

📌 Crear grupo
sudo groupadd guest
📌 Crear usuario y agregar al grupo
sudo adduser usuario_guest
sudo usermod -aG guest usuario_guest
📌 Eliminar usuario
sudo userdel -r usuario_guest

👉 -r elimina también su carpeta personal.

📌 Eliminar grupo
sudo groupdel guest
🔹 PRÁCTICA 4: Permisos de archivos
📌 Crear carpeta y archivo
mkdir materia
cd materia
touch estudiante.txt
📌 Editar con vi
vi estudiante.txt

👉 Presiona i para escribir
👉 Escribe nombre y matrícula
👉 ESC + :wq para guardar

📌 Permisos solo para el usuario
chmod 700 estudiante.txt

👉 Solo el dueño puede leer, escribir y ejecutar.

📌 Permisos solo para el grupo
chmod 070 estudiante.txt

👉 Solo el grupo tiene control total.

📌 Crear carpeta y copiar archivo
mkdir ../materia2
cp estudiante.txt ../materia2/
📌 Eliminar carpeta y contenido
cd ..
rm -r materia

👉 -r elimina carpeta y todo su contenido.


adduser	Crea un usuario
usermod	Modifica usuario
groupadd	Crea grupo
groupdel	Elimina grupo
chmod	Cambia permisos
cp	Copia archivos
rm -r	Elimina carpetas
vi	Editor de texto
ip	Configura red
netplan	Configuración permanente de red

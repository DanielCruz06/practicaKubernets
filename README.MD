# Instalar docker 
# --Desinstalar versiones anteriores
for pkg in docker.io docker-doc docker-compose docker-compose-v2 podman-docker containerd runc; do sudo apt-get remove $pkg; done

# actualizar librerias
sudo apt update

# instalar paqquetes 
sudo apt install apt-transport-https ca-certificates curl software-properties-common

# Agregar la clave GPG oficial de Docker:
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg

# Repositorio de docker
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

# Actualizar nuevamente los paquetes
sudo apt update

# Instalar docker
sudo apt install docker-ce docker-ce-cli containerd.io

# Verificar docker instalado
sudo systemctl status docker

# Ejecutar docker sin sudo
sudo usermod -aG docker $USER

# Prueba docker
sudo docker run hello-world

# -----------------------------------------------------------------

# Instalación de minikube 



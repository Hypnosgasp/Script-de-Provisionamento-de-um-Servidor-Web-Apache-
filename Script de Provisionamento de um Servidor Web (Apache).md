#!/bin/bash

# Atualiza o sistema operacional
sudo apt update && sudo apt -y upgrade

# Instala o Apache (servidor web)
sudo apt -y install apache2

# Habilita e inicia o serviço do Apache
sudo systemctl enable apache2
sudo systemctl start apache2

# Cria uma página index.html de exemplo
echo "<html><h1>Servidor Web Provisionado com Sucesso!</h1></html>" | sudo tee /var/www/html/index.html

# Exibe o status do serviço do Apache
sudo systemctl status apache2
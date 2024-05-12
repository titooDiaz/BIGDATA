<p align="center">
  <img width="150px" src="https://i.ibb.co/bXvzjXm/LOGO-h1.png" />
</p>


# PASOS A SEGUIR PARA INSTALAR MONGO DB en ubuntu (22.04)

Primero vamos a checar que realmente este usando esta version de ubuntu:

```bash
cat /etc/lsb-release
```

Ahora vamos a buscar la documentacion de (MongoDB)[https://www.mongodb.com/docs/manual/tutorial/install-mongodb-on-ubuntu/]

```bash
sudo apt-get install gnupg curl
```

```bash
curl -fsSL https://www.mongodb.org/static/pgp/server-7.0.asc | \
   sudo gpg -o /usr/share/keyrings/mongodb-server-7.0.gpg \
   --dearmor
```

```bash
echo "deb [ arch=amd64,arm64 signed-by=/usr/share/keyrings/mongodb-server-7.0.gpg ] https://repo.mongodb.org/apt/ubuntu jammy/mongodb-org/7.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-7.0.list
```

```bash
sudo apt-get update
```

Los siguientes comados son para instalar la ultiva version de MongoDB:

```bash
sudo apt-get install -y mongodb-org
```

```bash
echo "mongodb-org hold" | sudo dpkg --set-selections
echo "mongodb-org-database hold" | sudo dpkg --set-selections
echo "mongodb-org-server hold" | sudo dpkg --set-selections
echo "mongodb-mongosh hold" | sudo dpkg --set-selections
echo "mongodb-org-mongos hold" | sudo dpkg --set-selections
echo "mongodb-org-tools hold" | sudo dpkg --set-selections
```


Ahora vamos a iniciar mongoDB:

```bash
sudo systemctl start mongod
```

si no te deja iniciarlo puedes probar usar este comando antes:

```bash
sudo systemctl daemon-reload
```

Ahora verifiquemos que mongo db ya esta instalado:

```bash
sudo systemctl status mongod
```

cuando quieras pararlo puedes usar:

```bash
sudo systemctl stop mongod
```


Ahora vamos a instalar su version grafica:
para esto vamos a ir a la pagina de mongo nuevamnte: (aqui)[https://www.mongodb.com/docs/mongodb-shell/install/]

llave publica:

```bash
wget -qO- https://www.mongodb.org/static/pgp/server-7.0.asc | sudo tee /etc/apt/trusted.gpg.d/server-7.0.asc
```


ahora como estamos usando ubuntu 22.04 seleccionaremos esa opcion:

```bash
echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu jammy/mongodb-org/7.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-7.0.list
```

```bash
sudo apt-get update
```

Finalmente instalaremos:

```bash
sudo apt-get install -y mongodb-mongosh
```

Y comprobamos:

```bash
mongosh --version
```

```bash
mongosh
```

se abre por defecto 3 bases de datos, podemos verlas:

```bash
show dbs
```

Tambien seria una buena opcion instalar mngodb Compass
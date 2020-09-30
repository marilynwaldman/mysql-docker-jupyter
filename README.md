# docker-compose-mysql-with-adminer
Local MySQL = Docker + Docker Compose + MySQL Docker image + Adminer Docker image

taken from this tutorial:

https://medium.com/@tattwei46/how-to-use-python-with-mysql-79304bee8753

# Install docker if it is not installed

```aidl
sudo snap install docker
```

# Clone this repo on your ec2 instance

```aidl
git clone https://github.com/marilynwaldman/mysql-docker-jupyter.git
```

## Usage (start server)

On folder that contains `docker-compose.yml` type one of this.

```
// non detach mode
sudo docker-compose up
```
or
```
// detach mode
sudo docker-compose up -d
```

It will spin the MySQL latest version, expose port to host at 3306 and ready connection via Adminer or `mysql` CLI command.

## Usage (stop server)

To shutdown database without remove the container.

```
sudo docker-compose stop
```

To shutdown database and remove the container.
```
sudo docker-compose down
```

Is data that already created will gone? No, since in the Docker Compose file you can see that we utilize data container named `mysql_db_data_container` to store the MySQL data.

## MySQL credential

- Username: root
- Password: telluride

## How to connect to MySQL

### Via Adminer
Go to http://ec2 ....:8080

### Via command line
Make sure you have MySQL client installed and `mysql` command in CLI available.

```
mysql -uroot -ptelluride -h 127.0.0.1
```

or

```
mysql -uroot -prootpassword --protocol=TCP
```

Enjoy your local MySQL database server for any purpose you want, for me this setup is fine for testing purpose.

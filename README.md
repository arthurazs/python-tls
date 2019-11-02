# Simple TLS connection

This example was tested under Ubuntu 18.04.2 with python 3.6.8.

Open the terminal and enter the following commands:

```bash
user@pc:~$ sudo apt install git -y
user@pc:~$ git clone https://github.com/arthurazs/python-tls
```

The first command install git, the second command downloads this repository.

Note that `user@pc:~$` represents your username and computer name. You should type into the terminal only the text **after** the dollar sign, *e.g.* `sudo apt install git -y`.

## Generate the certificate and private key

Open the terminal and enter the following commands:

```bash
user@pc:~$ cd python-tls
user@pc:~/python-tls$ openssl req -new -x509 -days 365 -nodes -out cert.pem -keyout key.pem -subj "/C=BR/ST=Rio de Janeiro/L=Niteroi/O=UFF/OU=Midiacom/CN=127.0.0.1/emailAddress=arthurazs@midiacom.uff.br"
```

The first command changes the directory to the downloaded repository, the second command generates the certificate and private key.

Note that you can change some parameters:

- **C**, which is a 2 letter code for a country;
- **ST**, which is a state or province name;
- **L** *(optional)*, which is a city name;
- **O**, which is an organization name;
- **OU** *(optional)*, which is an organizational unit name;
- **CN**, which is the hostname:
  - **Warning** If you change the **CN** value, you have to change the hostname under [server.py](server.py) and [client.py](client.py) to reflect the new hostname.
- **emailAddress** *(optional)*, which is an email address.

## Running the TLS connection example

### Run the server example

Open the terminal and enter the following commands:

```bash
user@pc:~$ cd python-tls
user@pc:~/python-tls$ python3 server.py
```

### Run the client example

Open the terminal and enter the following commands:

```bash
user@pc:~$ cd python-tls
user@pc:~/python-tls$ python3 client.py
```

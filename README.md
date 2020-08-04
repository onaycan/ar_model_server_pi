<!-- TABLE OF CONTENTS -->
## Table of Contents

* [About the Project](#about-the-project)
* [Getting Started](#getting-started)
  * [Prerequisites](#prerequisites)
  * [Installation](#installation)
* [Usage](#usage)
* [License](#license)
* [Contact](#contact)
* [Acknowledgements](#acknowledgements)

<!-- ABOUT THE PROJECT -->
## About The Project

The main purpose of this small project to achieve stepwise a final goal: ar race car. 
In this little example i demonstrate a single server side application build by three.js.
The background image is selected on purpose as mono-static, which will be replaced with a stero-camera video stream. 
The VR part is taken from [sketchfab](sketchfab.com), the model of [ogonek](https://sketchfab.com/3d-models/ka-50-black-shark-full-cockpit-free-f8d37afc49fc4e9fac2aba54e9ed51f8)

### Built With
One major framewrok is used to achieve the goal: three.js. 
Additionally, a free model is chosen for the demonstration, which can replaced as user wishes to do it so.  
Special thanks goes to "ogonek" of sketchfab, for providing such a beatiful model to open-source community. 

* [threejs](https://threejs.org/)
* [Sketchfab](https://sketchfab.com/3d-models/ka-50-black-shark-full-cockpit-free-f8d37afc49fc4e9fac2aba54e9ed51f8)

![Image 1](./readme_pics/model_of_ogonek_sketchfab.png?raw=true "Model Chosen")


<!-- GETTING STARTED -->
## Getting Started

You need to fetch a local copy of these first.

### Prerequisites

Al the necessary prerequiests are included hereby. 
I prefered to use python to run the server, so make sure you have open ports in your machine and you know how to serve there. 
Under the directory certs, you will find the certificates i have created. I do not provide here the password for those, so feel free to create one using openssl. 

```shell
sudo apt install openssl
openssl genrsa -des3 -out server.key 2048
openssl req -new -key server.key -out server.csr
----
Common Name (e.g. server FQDN or YOUR name) []:-> ip of your server machiene (pi in my case goes here)
----
openssl x509 -req -days 2048 -in server.csr -signkey server.key -out server.crt
cat server.crt server.key > server.pem
..
.
```

### Installation

No needs of installation. 

<!-- USAGE EXAMPLES -->
## Usage
Simply run a server using python3's http.server on an open port, and navigate into your browser. 

```shell
you@yourmachine$ python3 -m http.server 5000
Serving HTTP on 0.0.0.0 port 5000 (http://0.0.0.0:5000/) ...
127.0.0.1 - - [03/Aug/2020 01:51:30] "GET / HTTP/1.1" 200 -
..
.
```
If you run on the client side (android in my case), the [arrc app - https://github.com/onaycan/ARRC](https://github.com/onaycan/ARRC), you will see the following on your mobile phone: 

![Image 2](./readme_pics/client_view.png?raw=true "Client View")


<!-- LICENSE -->
## License

Distributed under the MIT License as the major dependencies like three.js. 

<!-- CONTACT -->
## Contact

Oenay Can - onaycan@gmail.com

<!-- ACKNOWLEDGEMENTS -->
## Acknowledgements
* [threejs](https://threejs.org/)
* [Sketchfab](https://sketchfab.com/3d-models/cockpit-model-vr-33acf5be400740aa85d7738871231962)
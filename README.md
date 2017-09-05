# Linux_Server_Configuration

# 1. IP & SSH port )
## IP （13.229.26.176）
The server is hosted on the ip ```13.229.26.176```
## SSH port (22OO)
1. The default SSH port is shutdown both from the ```sshd.config``` and the firewalls;
2. The only port for SSH is  __2200__ 。
## HTTP port (80)
## NTP port （123）

# 2.URL for my web application
```agoodthing.cn```

# 3. Installed Software
1.python3
2.apache2
3.finger
4.emacs
5.mod_wsgi
6.postgresql

# 4.Configuration changes made

## SSH

1. Force Key Based Authentication 
```PasswordAuthentication no```
2. Set new port and disable port 22 
```
# Port 22 
Port 2200
```
3、Forbit the remote login of the root user 
```
PermitRootLogin no
```

## Apache2 (/etc/apache2/sites-enabled/000-default.conf)

Add this line of code below /var/www/html 
```
WSGIDaemonProcess website threads=5
WSGIScriptAlias / /var/www/html/website/website.wsgi

<Directory website>
    WSGIProcessGroup website
    WSGIApplicationGroup %{GLOBAL}
    Order deny,allow
    Allow from all
</Directory>
```
## google Oauth2.0
1. Add Authorized JavaScript origins
```http://agoodthing.cn```
```http://www.agoodthing.cn```
2. Authorized redirect URIs
```http://agoodthing.cn/login```
```http://agoodthing.cn/gconnect```
```http://www.agoodthing.cn/login```
```http://www.agoodthing.cn/gconnect```

# 5. Third party resouces 

### Module-flask
The python program import flask module to build up the whole app. In order to run the program properly, you should install **flask** at first

You can install **flask** with the code ```pip3 install flask```

### Module-sqlalchemy
The python program import sqlalchemy module to connect and manipulate the database. In order to run the program properly, you should install **sqlalchemy** at first

You can install **sqlalchemy** with the code ```pip3 install sqlalchemy```

### Module-oauth2client
The python program import oauth2client module to help using google's OAuth . In order to run the program properly, you should install **oauth2client** at first


# SSH Key
```
-----BEGIN RSA PRIVATE KEY-----
Proc-Type: 4,ENCRYPTED
DEK-Info: AES-128-CBC,24E4A7F6EE9E781D5869FD84A98EE01B

IBUMZJvY41tLu5lWvFRRvO32NNz7vwGCBTN/l41Dxf0Y4gmrqneLeEF9oaOtEnya
tWKm8TmT/k/a08Ww5hGNn0pFRi35/GqhxH9GihqKUQDNbtvAcxLcDastSiUGNHun
abG8WJlm3pQECwJApqraf7Ror6wp3Lz/crcCw9WtWY5s/uV3c77TY2NP8izTpQm+
nLQ5iKIYZfWR4s7ZhOqbEfZNfjwkkh7opN+sOGGOWipFtv3nDXsv6kdOXyEXwmAR
qQ81SLwRZmvm+JiUyySkrA76DOTVCVilWwhBN1YuVl+VRTwnufksjKu04SpGvugT
n/V8SSiunfV0/LIxe1TKHGiTa5PYfJVgkWkBAxm2K6E8eFRpLjEs7Pj6fy+fWBn7
z7miuDgiReT2hc2xfprFN+lg1/U4OyMBIetoKOiaVwHrrJZ0uzY3+t6+QeMMW8Io
35IGqLAu0xWUs5VeRXQwur8lhlWrHN6eO1epYZubzj2Ru0dpU00BNg+V0y30BfLg
XR7+W+xzGWJNZxXVnM4gHbSLfWkhTOfFNZ7m/yezWI3gfHo1xU1+A5s1S2Ytb0EC
yFSZYQEke4l1CNZcVi+qVm1tTX/0xqvPPToHz5ljUfGHCZtjqux95grwLdVg9m03
DG+1OrqJB9tTil6tqV093YAC6AedGQUK130Fr22mTPJDtV2maGO8Pmy4+GYn1wk/
jFLjTEufadetNXrzf81ZTVe9hSo2cSa2BRYw+tNKJFxblIkmAsGg6+qKimTQIG5E
gY7v+ImgJdEjgbQO0ceq3Mg5IO4so8F9OwVGYVR2R+M2HgHFmg8zAMX28zcMVuvL
4goAI7Xjfyg9CZAV/Yr/yInlmaARFBHa79kx/rn9rVHdL/395yBF3S1U9t7Qfmx6
m90GZxr1buCNPhirapVBxKeTWqnAk0tfUSOik37WdPyR519Wrq9R3mPIC3C49ukT
zcrY5NskyPC5smq1Jp+K34polu8p8Xc02BQdw344zPeatkcSMw2zBz63byJ5wr61
6tHWnv3hJpE7MK3xFCTi4Y+TNyxv3FlNQcvqYdiVw9KsmLGhk0eENNO8/4dbuCaC
j6lDMrTgm02hwy1BYH3b2V/YhcORZY7BLfVfvz+VxTE+7mXh9ntnpOQznvqZgcju
sVB/znFUS692PAcifv36viTgE0DBrgjzPQi6NimEFbCncP8M0Wftq8HKZxAHdA4S
DmBCQLxl9yZXrKeGqZjJ+PTCivaV+ArEqeDCHrFdBy5WoH0U7vjFu5E/7UdN/1U2
9OORihTxUUmORWxbrcdhTngoQJU5uqLZuqLrEmt4+XtOonaoErdLKwQG0OP5hInE
lPByhOJCUytjeetoigoO1ALv43nWU85NX9c/hCJ2zd8nMZniF78V6uuY2d/DLWO2
X+6zj7ImWn5eJhCMLLdNO7Ih6WpM6kl33+ZLlnPwG62E8/ycOpg7RvZk7rTB153g
4XcpXuspmSTm3BwRNAgjp/CkrVJVWnROX/+TomS/QTfoZZavTx5mocfu2IFmRAkD
T53u45BXuy8h/8M1LnSLyZ/2hK8Il+uGi4Nt16j7M/G51Y7P1kbciYIQCA7OYWIx
-----END RSA PRIVATE KEY-----
```
# Password for Grader
__udacity__

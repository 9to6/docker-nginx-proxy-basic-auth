# docker-nginx-proxy-basic-auth
Example to use Nginx-proxy on basic authentication.

## Set up your own password
Create file what is same name with your `VIRTUAL_HOST`.

And execute following commands.
```
$ echo -n '9to6:' >> ./htpasswd/whoami.local
```
Next, add an encrypted password entry for the username by typing:

```
$ openssl passwd -apr1 >> ./htpasswd/whoami.local
```

It's done now.

## Test

execute docker-compose.
```
$ docker-compose up
```  

curl test

```
curl 172.16.0.140:9091 --user 9to6:passwd
```

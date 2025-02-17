after installing and setting up nginx install certbot and the nginx plugin:
``` bash
sudo apt install certbot python3-certbot-nginx
```

Make sure nginx ports are open by:
- checking their status
``` shell
sudo ufw status
```

we need 'Nginx Full' enabled with:
``` shell
sudo ufw allow 'Nginx Full'
```

delete any other http etc, e.g.
``` shell
sudo ufw delete allow 'Nginx HTTP'
```

Your status should now look something like this:

```
sudo ufw status

```

```
OutputStatus: active

To                         Action      From
--                         ------      ----
OpenSSH                    ALLOW       Anywhere
Nginx Full                 ALLOW       Anywhere
OpenSSH (v6)               ALLOW       Anywhere (v6)
Nginx Full (v6)            ALLOW       Anywhere (v6)
```


register with certbot
``` shell
sudo certbot register
```

you will then enter emails and agree to terms and bits.

then to start cerifying use

``` shell
sudo certbot --nginx
```

it will then ask which site to certify, press enter to do them all.

it will then auto paste certificates into the code, these will probably need replacing but contain the right paths etc for your ssl cert! (and should keep it updated.)
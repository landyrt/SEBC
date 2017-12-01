The kinit command you use to authenticate your test user

```sh

[hduser@ip-172-31-26-122 ~]$ kinit landyrt@VINKOS.COM
Password for landyrt@VINKOS.COM: 

```

The output from a klist command listing your credentials and ticket lifetime

```sh

[hduser@ip-172-31-26-122 ~]$ klist
Ticket cache: FILE:/tmp/krb5cc_1001
Default principal: landyrt@VINKOS.COM

Valid starting     Expires            Service principal
29/11/17 13:09:11  30/11/17 13:09:11  krbtgt/VINKOS.COM@VINKOS.COM
	renew until 06/12/17 13:09:11

```

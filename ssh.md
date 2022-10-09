# Login by ssh
```
ssh -i ~/.ssh/zlalab_dev_id_rsa root@188.166.190.67
ssh -i ~/.ssh/zlalab_dev_id_rsa root@159.223.37.75
```


- Retrieve the public key for your key pair
```
ssh-keygen -y -f /path_to_key_pair/my-key-pair.pem
```

- 

```
chown $USER ~/.ssh/config

chmod 400 ~/.ssh/id_rsa
```
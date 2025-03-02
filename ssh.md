# Login by ssh
```
ssh -i ~/.ssh/zlalab_dev_id_rsa root@ip -o ServerAliveInterval=3600 
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
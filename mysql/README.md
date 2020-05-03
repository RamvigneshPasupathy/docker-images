# "my.cnf" is copied out of a running mysql docker container

docker container exec -it <container-id> /bin/bash
cat /etc/mysql/my.conf

# copied the file content and pasted out to our new new "my.cnf" outside the container in the host machine

---

# "secure-file-priv" is updated in the "my.cnf" to enable "SELECT .. OUTFILE" exports

---

# in case of an error like this: "Can't create/write to file .. Permission denied"
## get into the container
docker container exec -it <container-id> /bin/bash
## change permissions to the outfiles directory
chmod -R a+rwx /home/outfiles

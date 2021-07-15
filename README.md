# Use Rancher 1.x UI to add ssh key to host nodes for ssh access.

- On rancher environment with disabled ssh access, add stack -> paste below compose and run.
- Click on the getroot service from the top level stack view, on container level view click on the three dots menu on top right. 
- Select execute shell.
- You can now add ssh public keys to ~/.ssh/ and or scripts to rc.local / upstart / init.d to provision or recover access.


```
getroot:
  image: alpine:latest
  stdin_open: true
  tty: true
  entrypoint: /bin/sh
  volumes:
    - /:/root
  
#Import this docker compose file using the add stack option of Rancher.  Once running navigate to the node and then Execute Shell from the menu, you now own the host this container runs on.
```

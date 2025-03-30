1. Buy/Get a free remote server. (I used a free plan from [DigitalOcean](https://www.digitalocean.com/))
2. Create a Droplet - set up the data center, server plan, OS, enable SSH key authentication, and add a local SSH key.
3. Add an additional SSH key later on:
   1. Connect to the server with `ssh root@your-server-ip`
   2. `mkdir -p ~/.ssh`
   3. `chmod 700 ~/.ssh`
   4. From the local terminal, run:  
      ```sh
      ssh-keygen -t rsa -b 4096 -f ~/.ssh/key1 -C "key1"
      ```
   5. `ssh-copy-id -i ~/.ssh/key1.pub root@your-server-ip`
   6. On the remote server, run:  
      ```sh
      chmod 600 ~/.ssh/authorized_keys
      ```
   7. Restart SSH:  
      ```sh
      systemctl restart ssh
      ```
4. Connect to the server using:  
   ```sh
   ssh -i ~/.ssh/key1 root@your-server-ip

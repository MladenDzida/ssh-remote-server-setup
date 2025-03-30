# ssh-remote-server-setup
Basic setup steps for a remote linux server with SSH connections. (https://roadmap.sh/projects/ssh-remote-server-setup)

The steps of setting up a remote linux server with SSH connections:
<ol>
  <li>Buy/Get a free remote server. (I used a free plan from [DigitalOcean](https://www.digitalocean.com/) )</li>
  <li>Create a Droplet- set up the data center, server plan, os, enable ssh key authentication and add a local ssh key</li>
  <li>Add additional ssh key later on:
    <ol>
      <li>connect to the server with ssh root@your-server-ip</li>
      <li>mkdir -p ~/.ssh</li>
      <li>chmod 700 ~/.ssh</li>
      <li>from local terminal run "ssh-keygen -t rsa -b 4096 -f ~/.ssh/key1 -C "key1"</li>
      <li>ssh-copy-id -i ~/.ssh/key1.pub root@your-server-ip</li>
      <li>on the remote run "chmod 600 ~/.ssh/authorized_keys"</li>
      <li>on the remote run "systemctl restart ssh"</li>
    </ol>
  </li>
  <li>connect to the server using: ssh -i ~/.ssh/key1 root@your-server-ip</li>
</ol>

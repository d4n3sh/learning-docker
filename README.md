# Learning Docker

## Installing Docker on Fedora Server 36

Official install guide: [Install Docker Engine on Fedora](https://docs.docker.com/engine/install/fedora/)

1. Add repo
  
```bash
# sudo dnf config-manager --add-repo https://download.docker.com/linux/fedora/docker-ce.repo
```

2. Install Docker Engine

```bash
# sudo dnf install docker-ce docker-ce-cli containerd.io docker-compose-plugin
```

3. Enable and verify that Docker is working.

```bash
# sudo systemctl enable --now docker

# sudo docker run hello-world
Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
2db29710123e: Pull complete
...
Hello from Docker!
This message shows that your installation appears to be working correctly.
``

4. Add user to the "docker group".

```bash
# sudo usermod -a -G docker danesh

# docker run hello-world

Hello from Docker!
This message shows that your installation appears to be working correctly.
```
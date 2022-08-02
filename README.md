# Running project with local monitoring

If you want to check metrics (celery and cpu-memory metrics from cAdvisor are available now) follow this instruction.

Before start create `./prometheus-data/data` in project directory by:
```
mkdir -p prometheus-data/data
```

Give necessary permissions
```
sudo chmod 777 /var/run/docker.sock
sudo chmod 777 /var/run/docker-cli.sock
```


1. Find the directory where docker stores their data:
* for ubuntu `/var/lib/docker`;
* for wsl2 `\\wsl$\docker-desktop-data\version-pack-data\community\docker`;
* your own directory.

To check the directory for emptiness.
```bash
ls your/path/to/docker
```

2. Mount your docker directory to `/var/lib/my_docker` (for wsl2 users)

If you already have `/var/lib/my_docker`, delete it and create it again:
```bash
sudo rm -rf /var/lib/my_docker && sudo mkdir /var/lib/my_docker

```


```bash
sudo mount -t drvfs '\\wsl$\docker-desktop-data' /var/lib/my_docker
```


3. After starting up open the [grafana](http://localhost:3030)
    * username: admin
    * password: admin

Skip password changing. Then click `dashbords\browse` and choose required dashboard.


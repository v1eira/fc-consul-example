Bring up the app running:
```bash
docker-compose up -d
```

Enter each container to register the service:
```bash
docker exec [container-name] -it sh
consul agent -config-dir=/etc/consul.d
```

Make the clients join the cluster:
```bash
consul join [server.ip]
```

Install dig to check the services status. So, inside the container, run:
```bash
apk -U add bind-tools
```

Use dig to discover services:
```bash
dig @localhost -p 8600 nginx.service.consul
```
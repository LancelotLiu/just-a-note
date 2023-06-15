* https://hub.docker.com/_/redmine
* https://hub.docker.com/_/postgres
* podman pull redmine:5.0.5
* podman pull postgres:15.3
* podman network create redmine-network
* podman run -d --name postgres --network redmine-network -e POSTGRES_PASSWORD=secret -e POSTGRES_USER=redmine postgres:15.3
* podman run -d --name redmine --network redmine-network -e REDMINE_DB_POSTGRES=postgres -e REDMINE_DB_USERNAME=redmine -e REDMINE_DB_PASSWORD=secret -p 3000:3000 -v /mnt:/mnt redmine:5.0.5

# 用 grafana 存取 redmine 的 posgre
* podman run -d --network redmine-network --name=grafana -p 4000:3000 grafana/grafana-oss:9.5.3

# TODO
* 使用 YAML 建立 pod for redmine
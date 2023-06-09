* 切換 podman 指令要連到的 machine
```
podman system connection default machine-name
```
* podman with wsl2 不確定甚麼原因下會導致 podman machine 的 service port 無法 forwarding 到本機
  * 參考 https://jwstanly.com/blog/article/Port+Forwarding+WSL+2+to+Your+LAN/
  * 手動設定 port forwarding
    ```
    netsh interface portproxy add v4tov4 listenport=[PORT] listenaddress=0.0.0.0 connectport=[PORT] connectaddress=[WSL_IP]
    ```


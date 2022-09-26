<img src="https://raw.githubusercontent.com/google/cadvisor/master/logo.png">  

----
# Intro
此開源工具可用於監控Container效能，以利於效能優化以及維護。  
本工具使用docker包裝，使用前請先確認系統已安裝docker
  
  
# How to use
- Install  
```
sudo docker run \
  --volume=/:/rootfs:ro \
  --volume=/var/run:/var/run:ro \
  --volume=/sys:/sys:ro \
  --volume=/var/lib/docker/:/var/lib/docker:ro \
  --volume=/dev/disk/:/dev/disk:ro \
  --publish=8080:8080 \ # 設定port號
  --detach=true \
  --name=cadvisor \ # 設定container name
  --privileged \
  --device=/dev/kmsg \
  gcr.io/cadvisor/cadvisor:latest
```
- Use  
根據上述指令所建立之環境，container build起來後，可於localhost:8080看見監控頁面

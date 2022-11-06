# Project ISY Server

Docker hub link.

Current version: `newgameserver-1.0`

Default password: `secret`

## Building the image

1. Download the latest version from blackboard (it is unlikely that it has been updated but you never know). Copy it to this folder and name it `server.jar`.
1. Run the following:

```bash
docker build -t jonavdm/isy-server .
docker run --rm --name isy-server -p 7789:7789 -p 8081:8081 jonavdm/isy-server
```

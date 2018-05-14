# How to Install Ghost with Docker
This article will give you a brief introduction to how to install [ghost](https://ghost.org/) with [Docker](https://www.docker.com/).
The content will be:
1. Environment
2. Instruction
# Environment
## Host
- OS: `Ubuntu 16.04.2 LTS`
- Kernel: `4.4.0-124-generic`

## Docker
- Version: `17.04.0-ce`

## Ghost
- Version: `1.22.7`

# Instruction
1. Spin up your Ghost server:
```
docker run -d --name ghost \
           -e url=http://YOUR-DOMAIN-HERE \
           -p 80:2368 \
           -v /YOUR-PATH-TO-PERSIST-DATA:/var/lib/ghost/content \
           ghost:1.22.7-alpine
```

2. Tail log until intialized:
```
docker logs -f ghost
```
When you see the following logs means your server is ready to serve:
```
[2018-05-14 12:47:23] INFO Ghost is running in production...
[2018-05-14 12:47:23] INFO Your blog is now available on http://YOUR-DOMAIN-HERE
[2018-05-14 12:47:23] INFO Ctrl+C to shut down
[2018-05-14 12:47:23] INFO Ghost boot 8.047s
```

3. Head to `http://YOUR-DOMAIN-HERE` to see your blog
4. Head to `http://YOUR-DOMAIN-HERE/ghost` to access your blog admin area

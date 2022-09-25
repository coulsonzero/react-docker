# docker 部署 react 前端项目

1. 创建react项目，并下载依赖包
```sh
$ npx create-react-app react-docker
$ yarn
# $ yarn start
# $ yarn build
```

2. 使用docker部署react项目

- 2.1 Dockerfile

```Dockerfile
FROM node:14-alpine
WORKDIR /code
ADD . /code
RUN yarn
EXPOSE 3000
CMD npm start
```

- 2.2 docker部署命令

```sh
$ docker build -f Dockerfile -t react-docker:v1 .
$ docker run -d -p 80:3000 --name react-docker react-docker:v1
```

- 2.2 查看镜像
```sh
$ docker --version
$ docker images
$ docker ps -a
```

[https://localhost]([https://localhost:80/])
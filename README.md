# Drone on localhost

<img src="/docs/img/demo.png" alt="Register Oauth" style="max-width:5%;">

Based on
- [drone.io 1.0を使ってみる](https://qiita.com/mmhiyoko/items/7669e44652052468fb3b)

## TL; DR
- Run Ngrok

```
gkz@localhost /usr/bin $ ./ngrok http $PORT
```

- Open aother termial
```
gkz@localhost ~/workspace/drone-sample (master) $ openssl rand -hex 16
cccccccccccccc
gkz@localhost ~/workspace/drone-sample (master) $ tail ~/.bashrc
export DRONE_GITHUB_CLIENT_ID=aaaaaaaaaaa
export DRONE_GITHUB_CLIENT_SECRET=bbbbbbbbbbbbb
export DRONE_RPC_SECRET=cccccccccccccc          # openssl rand -hex 16
export DRONE_SERVER_HOST=hogehoge.ngrok.io
gkz@localhost ~/workspace/drone-sample (master) $ docker-compose up -d --build
```

## Technologies Used
- Docker 19.03.4
  - drone/drone:1
- docker-compose 1.24.1

## Notes

- Register a new OAuth application

<img src="/docs/img/register_oauth.png" alt="Register Oauth" style="max-width:5%;">


- [Ngrok Tutorial](/docs/ngrok_tutorial.md)
Run in docker
```
export APP_NAME=myetherwallet

cd ~/projects/webrepo/$APP_NAME

docker build -t lasery/webrepo-$APP_NAME .

docker run --rm -it --name=webrepo-$APP_NAME \
  -v $PWD/app:/usr/src/app \
  --net=host --pid=host \
  lasery/webrepo-node-request-context \
  bash
```

Usefull commands
```
npm install
node inspect
```

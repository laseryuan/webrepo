```
export APP_NAME=\
{app_name}

cd ~/projects/webrepo/archive/$APP_NAME
ln -s ../node_modules ./
```

Run in docker
```
docker build -t lasery/webrepo-$APP_NAME .

docker run --rm -it --name=webrepo-$APP_NAME \
  -v $PWD/app:/usr/src/app \
  --net=host --pid=host \
  lasery/webrepo-node-request-context \
  bash

  --env-file ../../admin/env.list \
```

Copy node_modules source code to local directory
```
  mkdir node_modules
  docker run --rm \
    -v $PWD/node_modules/:/tmp/node_modules/ \
    lasery/webrepo-$APP_NAME \
    cp -rf ../node_modules/. /tmp/node_modules/
```

Usefull commands
```
npm install
node inspect
```

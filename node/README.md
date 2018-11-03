Run in docker
```
cd ~/projects/webrepo/node

docker build -t lasery/node .

docker run --rm -it --name=node \
  -v $PWD/node:/node \
  --net=host --pid=host \
  lasery/node \
  bash
```

Inspect
```
./node inspect test/parallel/test-stream2-transform.js
```

Internal lib
```
./node --expose-internals test/parallel/test-repl-preprocess-top-level-await.js

```

Repl await
```
./node --expose-internals --experimental-repl-await test/parallel/test-repl-top-level-await.js

```

Find corrent paramter to run node test
```
tools/test.py -v -J test/parallel/test-repl-top-level-await.js

```

Comiple and Build
```
./configure && make -j4

make -j4
make -j4 test
```

# Work in process
    ```
    ./node inspect --expose-internals --experimental-repl-await test/parallel/test-async-hooks-promise.js
    ```

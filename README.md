# docker-esp-open-sdk
Dockerfile for https://github.com/pfalcon/esp-open-sdk

# build

```bash
docker build . -t wuyue/esp-open-sdk
```

# build micropython for esp8266

```
git clone https://github.com/micropython/micropython
cd micropython
git submodule update --init

docker run -it --device=/dev/ttyUSBx -v ${PWD}:/opt/micropython wuyue/esp-open-sdk /bin/bash

# inside docker

cd /opt/micropython
make -C mpy-cross
cd ports/esp8266
make
```
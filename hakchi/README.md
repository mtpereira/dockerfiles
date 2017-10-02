# Build

```
git clone git@github.com:madmonkey1907/hakchi.git
cd hakchi
git submodule init
git submodule update
```

Copy these files over that directory and run:

`docker build --rm --tag hakchi .`

# Run

Run `xhost local:root` to allow your X11 server to be accessed from the container.

Find the bus and device IDs of your device using `lsusb -v` and then run:

```
docker run \
  --rm -it \
  --device /dev/bus/usb/__BUS_ID__/__DEVICE_ID__ \
  -e DISPLAY=unix$DISPLAY \
  -v /tmp/.X11-unix:/tmp/.X11-unix \
  hakchi
```


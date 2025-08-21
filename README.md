This serves as a complete & simple example to test gamepad support (I was troubleshooting https://github.com/raysan5/raylib/issues/3651).

I use cmake:

```sh
# build/run native
cmake -G Ninja -B build -DCMAKE_BUILD_TYPE=Release
cmake --build build
./build/raylib-gamepadtest

# build/run web
emcmake cmake -G Ninja -B wbuild -DCMAKE_BUILD_TYPE=Release
cmake --build wbuild
npx -y live-server wbuild --open=raylib-gamepadtest.html
```
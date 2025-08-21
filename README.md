This serves as a complete & simple example to test joystuick support (I was troubleshooting https://github.com/raysan5/raylib/issues/3651).

I use cmake:

```sh
# build native
cmake -G Ninja -B build -DCMAKE_BUILD_TYPE=Release
cmake --build build

# build web
emcmake cmake -G Ninja -B wbuild -DCMAKE_BUILD_TYPE=Release
cmake --build wbuild
```
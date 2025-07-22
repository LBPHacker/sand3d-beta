# ey look lbphacker made it build

## changes I made

- add a meson config, install meson and ninja with your package manager
	- pull glm and glfw via the package ecosystem, install them with your package manager
	- resolution of those two dependencies requires cmake, install it with your package manager
	- assuming codebase to be c++17
- add glad, fastnoiselite, and stb as submodules
- include glm headers through the correct include path, i.e. with an extra `glm/` path component
- rename `solid::color` and `text::color` to `::mycolor` in both cases, since `color` is already a type
- fix `.xyz` swizzle by calling it as a function (as intended? idk)

## building the thing

Init the git submodules with
```sh
$ git submodule update --init
```

The package manager steps are supposed to be as simple on msys2 ucrt64 as
```sh
$ pacman -Syu # make sure everything is up to date
$ pacman -S --noconfirm --needed mingw-w64-ucrt-x86_64-{glfw,glm,meson,ninja,gcc,cmake}
```
The packages are named similarly on most package ecosystems.

Then building the thing is as simple as
```sh
$ meson setup build-debug
$ (cd build-debug && meson compile)
$ ./build-debug/sand3d # maybe add .exe on windows
```

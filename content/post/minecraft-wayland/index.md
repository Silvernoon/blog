+++
date = '2026-08-12'
title = 'minecraft在wayland下严重卡顿问题'
tags = ['linux','minecraft','wayland']
+++

官方glfw对wayland支持极其低下，但是我们有非官方patch

aur用户可以选择这个：
<https://aur.archlinux.org/packages/glfw-wayland-minecraft-cursorfix>

非aur：
<https://github.com/jdkeke142/glfw-wayland-minecraft>
<https://github.com/BoyOrigin/glfw-wayland>

然后，如果用hmcl，把使用系统glfw勾上，注意不要勾openal
或者 -Dorg.lwjgl.glfw.libname=/usr/lib/libglfw.so

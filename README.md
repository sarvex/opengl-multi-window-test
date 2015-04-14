# Multi Window OpenGL Test

This repository is to figure out the answer to this question:

http://stackoverflow.com/questions/29617370/multiple-opengl-contexts-multiple-windows-multithreading-and-vsync

## Building And Running

```
clang -Werror -Wall -g -o multi-window-test main.c -lglfw -pthread
./multi-window-test --windows 6
```

Now watch stderr and see the fps reported should be really close to 60, not
60 / (whatever you set --windows to)

## Results

 * Linux, X11, 4.4.0 NVIDIA 346.47 (2015-04-13)
   - frame rate is 60fps no matter how many windows are open.
 * OSX 10.9.5 (2015-04-13)
   - frame rate is not capped; swap buffers is not blocking.

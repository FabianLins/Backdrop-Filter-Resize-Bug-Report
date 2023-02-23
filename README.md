# Backdrop-Filter-Resize-Bug-Report-And-Fix

Demo:
https://fabianlins.github.io/Backdrop-Filter-Resize-Bug-Report-And-Fix

Problem:
If you resize a container with a backdrop-filter: blur propoerty if does not affect the area out of the window.

Worksaround:
Add a minimal blur effect.

Before:
```console
.blur {
    width: 100%;
    height: 100vh;
    background: rgba(255, 0, 0, .3);
    position: fixed;
    z-index: 2;
    backdrop-filter: blur(20px);
}
```


After:
```console
.blur {
    width: 100%;
    height: 100vh;
    background: rgba(255, 0, 0, .3);
    position: fixed;
    z-index: 2;
    backdrop-filter: blur(20px);
    filter: blur(0.01px);
}
```

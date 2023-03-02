# Chrome-Backdrop-Filter-Resize-Bug-Report-And-Fix

Demo:
https://fabianlins.github.io/Chrome-Backdrop-Filter-Resize-Bug-Report-And-Fix

Problem:
If you resize a container with a backdrop-filter: blur propoerty if does not affect the area out of the window.
It appeared on Chrome. Firefox did not have this issue.

Versions:
It appears in Version 112.0.5596.2 (Official Build) dev (arm64).
It is already fixed in Version 113.0.5626.0 (Official Build) canary (arm64).


Work around:
Add a 0px blur effect.

Before:
```console
.blur {
    width: 100%;
    height: 100vh;
    background: rgba(255, 0, 0, .3);
    position: fixed;
    z-index: 2;
    backdrop-filter: blur(20px);
    //filter: blur(0px);
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
    filter: blur(0px);
}
```

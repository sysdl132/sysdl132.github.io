# Guide to convert scratch project to .exe

#### What you need:

* a scratch project(.sb .sb2 .sb3)
* NWJS sdk
* htmlifier tool

#### NWJS 0.44.1 downloads

[win-x64](https://dl.nwjs.io/v0.44.1/nwjs-v0.44.1-win-x64.zip)

[win-x86](https://dl.nwjs.io/v0.44.1/nwjs-v0.44.1-win-ia32.zip)

[mac-x64](https://dl.nwjs.io/v0.44.1/nwjs-v0.44.1-osx-x64.zip)

No mac-x86

[linux-x64](https://dl.nwjs.io/v0.44.1/nwjs-v0.44.1-linux-x64.tar.gz)

[linux-x86](https://dl.nwjs.io/v0.44.1/nwjs-v0.44.1-linux-ia32.tar.gz)

NOTE|linux is .tar.gz other is .zip

[arm](https://github.com/LeonardLaszlo/nw.js-armv7-binaries)

China too slow?[click me!](http://npm.taobao.org/mirrors/nwjs/v0.44.0-beta1/)

---

#### Steps:

1.Download NWJS by follow link.

2.go to htmlifier:

my link: https://sysdl132.gitee.io/htmlifier/

other link:  https://sheeptester.github.io/words-go-here/htmlifier/

3.Follow:

![img1](https://github.com/sysdl132/sysdl132.github.io/blob/master/141523_0a2d2916_5676984.png?raw=true)

I.select your project(ID:https://scratch.mit.edu/projects/ **310161394(ID)** /  or  upload).

II.Select the title of the window(see down/project name) and the username block value.

![img2](https://github.com/sysdl132/sysdl132.github.io/blob/master/142311_671a8e48_5676984.png?raw=true)

III.choose your options

|options|turn on will..|
|-----|-----|
|show fullscreen button?|enable fullscreen button|
|enable turbo mode?|enable turbo mode|
|use custom variable/list color?|change color of variables and lists|
|Load progress indicator?|Load progress indicator|
|Enable compatibility mode?|set highest FPS to 30(else:60)|
|Does this project use a custom size?|custom window size|
|Cloud variable source|set cloud variable source|

IV.click "HTMlify"

4.Download file and move into NWJS folder.

5.Create package.json:

```
{
  "name": "your_window_default_title",
  "main": "your_html_file_name.html"
}
```

6.Execute nw.exe and run!

# Advanced option--compile into a single file.

Use makesfx.exe(search on google) to pack them into a single .exe

Download at: https://revocue.cz/en/make-sfx/index.php

![img3](https://github.com/sysdl132/sysdl132.github.io/blob/master/143923_fc5c3e6a_5676984.png?raw=true)

1.set your NWJS folder.

2.set your output ``.exe``.

3.set your nw.exe in your folder.

4.click``Make SFX``.

[<back](https://sysdl132.gitee.io/htmlifier)

If you have any problem,create an issue.

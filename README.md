# Discussions on Yue

You can ask any question about Yue in the Issues page here, but please do not expect to get an answer.

## FAQ

### What does Yue mean?

It means moon in Chinese.

### Why a new GUI library? / What's the differences between Yue and XXX?

When writing GUI programs, I had been searching for a library that:

* Uses native widgets;
* Works on all major desktop platforms;
* Has a modern and clean C++ interface;
* Has good support for High DPI;
* Uses windowless controls on Windows;
* Generates small executable size;
* Friendly license for closed source apps.

There were lots of good GUI toolkits, but I could not find one that meets all above conditions, so I decided to write my own.

### Do I need to open source my project when using Yue?

As long as you do not modify Yue's source code, there is no requirements on which license you should use for your project. You can link your project with Yue statically or dynamcially, or even compile Yue's source code as part of your project.

But once you have done modifications to Yue's source code, all your code linked with Yue have to be open sourced with MS-RL. The only way to remove this limitation is to subscribe to [Yue's paid plan][paid-plan].

### The license seems like a non starter.

Note that the license of Yue has less restrictions than LGPL, it does not require you to open source your project when you statically link with Yue, or compile Yue's source code as part of your project.

So if you are fine with LGPL libraries, there is no reason to worry about Yue's license.

Yue is just another open source project with dual licenses, and it has __less__ restrictions than most dual licenses projects.

### The license indicates that I have to rely on you to make changes I need, otherwise I have to pay or open source my project?

Yes, and it is true for most dual licences projects.

But note that with Yue you only have to pay __once__ if you just want to fork Yue without changing your project's license, you only need to pay monthly if you want to keep getting updates.

### Can I trust you on this project?

I had been the solo developer of [Electron](https://electron.atom.io) and [node-webkit](https://github.com/nwjs/nw.js) (now known as NW.js) for a very long time, and today big corps are building their new apps on them. So I think it should not be hard to be confident about Yue.

(If you are wondering, it is still my full-time job working on Electron.)

### Having issues reported can make your software better, charging for it is not wise.

I know, and probably I know it better than you, I have been a long time open source project maintainer.

And you can report your issue to [yue/help](https://github.com/yue/help), I'll read them, it is just I will only reply to some of them.

### Your website looks shabby.

But it has a good documentation site.

### Is there a roadmap?

[Yue Roadmap](https://github.com/yue/yue/blob/master/docs/development/roadmap.md).

### Will Yue support XAML/QML?

No, Yue will always be a widgets library, there is no plan to implement high level languages like XAML/QML in Yue. The goal of Yue is to provide a low-level library that can be used to easily implement things like Rect Native and XAML/QML.

However Yue will support creating widgets from simple XML descriptions, since it is essential for writing a visual GUI builder.

### Will Yue support CSS?

No.

### What's the minimum version of Windows supported?

By using Win32 API and GDI+, Yue can work on Windows >= 7. It is also possible to make Yue work on Windows XP with some efforts, but this is not on my roadmap.

### Are all widgets windowless on Windows?

No, currently text input related widgets are still implemented by using Win32 Common Controls, becuase it is rather tough to implement a text input widget from scratch, and I have to focus on more important things first.

In future I'll make all widgets windowless, but it might be optional since it may bloat the size of executable.

### Can I embed a web browser in Yue?

Currently there are efforts on supporting native webview in Yue, e.g. `WebView` on macOS, `webkitgtk` on Linux, and Internet Explorer on Windows.

### Can I embed Chrome in Yue?

It should be possible to embed [CEF][cef] into Yue, but it would take lots of efforts and currently not on my roadmap.

### Can I use Yue in Electron?

Yes it is [supported][yue-js]. However it should be noted that currently it is not possible to embed `WebContents` of Electron into windows created by Yue, it could be supported but would need great efforts on both Electron and Yue's sides, and it is not on my roadmap.

### Can I use Yue in NW.js?

No it is not possible, Yue requires to be used in the UI thread of the main process, which is not supported by NW.js.

### When will Yue be stable when running in Node.js?

Probably never. Node.js has its own libuv event loop that can not run together with the GUI event loop required by Yue, currently the Node.js binding of Yue replaces the event loop of Node.js, but it has so many problems that are probably never going to be fixed.

My plan is to provide a custom distribution of Node.js that uses GUI event loop instead, like how Electron is implemented, so users can run Yue in it without hacks.

[paid-plan]: https://github.com/yue/yue/tree/master/docs/paid_plans
[cef]: https://bitbucket.org/chromiumembedded/cef
[yue-js]: http://libyue.com/docs/v0.1.0/js/guides/getting_started.html

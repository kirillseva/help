# Discussions on Yue

You can ask any question about Yue in the Issues page here, but please do not expect to get an answer.

## FAQ

### Do I need to open source my project when using Yue?

As long as you do not modify Yue's source code, there is no requirements on which license you should use for your project. You can link your project with Yue statically or dynamcially, or even compile Yue's source code as part of your project.

But once you have done modifications to Yue's source code, all your code linked with Yue have to be open sourced with MS-RL. The only way to remove this limitation is to subscribe to [Yue's paid plan][paid-plan].

### Is there a roadmap?

[Yue Roadmap](https://github.com/yue/yue/blob/master/docs/development/roadmap.md).

### What's the minimum version of Windows supported?

By using Win32 API and GDI+, Yue can work on Windows >= 7. It is also possible to make Yue work on Windows XP with some efforts, but this is not on my roadmap.

### Can I embed a web browser in Yue?

Currently there are efforts on supporting native webview in Yue, e.g. `WebView` on macOS, `webkitgtk` on Linux, and Internet Explorer on Windows.

### Can I embed Chrome in Yue?

It should be possible to embed [CEF][cef] into Yue, but it would take lots of efforts and currently not on my roadmap.

### Can I use Yue in Electron?

Yes it is [supported][yue-js]. However it should be noted that currently it is not possible to embed `WebContents` of Electron into windows created by Yue, it could be supported but would need great efforts on both Electron and Yue's sides, and it is not on my roadmap.

### Can I use Yue in NW.js?

No it is not possible, Yue requires to be used in the UI thread of the main process, which is not supported by NW.js.

[paid-plan]: https://github.com/yue/yue/tree/master/docs/paid_plans
[cef]: https://bitbucket.org/chromiumembedded/cef
[yue-js]: http://libyue.com/docs/v0.1.0/js/guides/getting_started.html

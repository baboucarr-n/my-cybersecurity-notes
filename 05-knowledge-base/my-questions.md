# My Questions

## 10 February 2026

**I still don't fully understand why everything in Linux is considered a file. How can a "file" perform complex tasks?**

Still an open question for me -- need to dig into this more. My rough guess so far is that "file" in Linux doesn't just mean a text document, it means any interface that can be read from or written to (like device files, sockets, pipes), and the kernel treats them all the same way through that file abstraction. Haven't fully confirmed this yet though.
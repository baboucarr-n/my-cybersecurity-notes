# Package Manager

## Managing Packages (Basically Software)

### What Are Linux Packages

Software you know by name -- Chrome, Firefox -- is technically a package on Linux. A package is an archive bundling everything the application needs: executables, config files, documentation, all packaged together.

Different distros use different package formats. Debian/Ubuntu-based systems use .deb packages, while Red Hat/Fedora-based systems use .rpm. That's part of why a package built for one distro won't just install on another without conversion.

### The Software Packet Chain

This is basically the journey a piece of software goes through before it ends up installable on your system:

**Upstream Providers** -- the actual developers. They write the software, ship it, create the documentation, and deploy it.

**Package Maintainers** -- once upstream releases a new version, maintainers take it, review it, and package/distribute it in a form that different distros can actually install (deb, rpm, etc).

### What Is a Package Repository

A repository is a central storage location for software, hosted on servers across the internet. It holds curated collections of packages for a given distro, so you don't have to manually track down and download software yourself -- your package manager just pulls from the repo.

### Archiving vs Compression

These get confused but they're different things:

- **Archiving** -- combining multiple files/directories into a single file (an archive), mainly to make managing and transferring a group of files easier. tar does this.
- **Compression** -- reducing file size to save disk space and speed up transfers. gzip does this.

You'll often see tar and gzip used together -- tar bundles the files, gzip shrinks the result (that's where .tar.gz comes from).

### Compressing Single Files with gzip

gzip compresses individual files. Once compressed, the original file gets replaced by one with a .gz extension.

```
gzip theFileName
```

To reverse it and get the original file back:
```
gzip -d theFileName.gz
```

(-d for decompress. Worth knowing since you'll need it just as often as compressing.)
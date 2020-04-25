# asdf-java

[Java](https://www.java.com/en/) plugin for the [asdf](https://github.com/asdf-vm/asdf) version manager.

## Why this repository

This repository is mostly based on the official [asdf-java](https://github.com/halcyon/asdf-java).
Because in China, the download speed for AdoptOpenJDK is very slow. So I just
change the final download link to [TUNA mirror](https://mirrors.tuna.tsinghua.edu.cn/AdoptOpenJDK).
This is only useful for China users, and the code changes are a bit invaded, so
it's better to keep these changes in the forked repository.

## Requirements
- [jq](https://stedolan.github.io/jq/)
- [curl](https://curl.haxx.se/)
- [sha256sum](https://www.gnu.org/software/coreutils/)

## Install

```
asdf plugin-add java https://github.com/uzxmx/asdf-java.git
```

## Use

Check [asdf](https://asdf-vm.github.io/asdf/) for instructions on how to install & manage versions of Java.

If you experienced the error like below, most probably it's because of TUNA only
mirrors the latest JDK version for each variant. So you need to update your local
JDK version to resolve this issue.

```
OpenJDK11U-jdk_x64_linux_hotspot_11.0.6_10.tar.gz
OpenJDK11U-jdk_x64_linux_hotspot_11.0.6_10.tar.gz: FAILED
sha256sum: WARNING: 1 computed checksum did NOT match
```

## Install

List candidate JDKs:

`asdf list-all java`

Install a candidate listed from the previous command like this:

`asdf install java adopt-openjdk-12.0.2+10.2`

Select an installed candidate for use like this:

`asdf global java adopt-openjdk-12.0.2+10.2`

## JAVA_HOME

I do not recommend the [way](https://github.com/halcyon/asdf-java#java_home) as the official says,
because that may slow your shell startup speed. Instead, I recommend adding
below line to your shell rc file explicitly.

```sh
export JAVA_HOME=~/.asdf/installs/java/YOUR_JDK_VERSION
```

Change YOUR_JDK_VERSION to the correct value. Remember to update it whenever
you want to change to a different JDK version.

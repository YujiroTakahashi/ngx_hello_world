# ngx_hello_world

## ビルドツールのインストール
```
$ wget http://hg.nginx.org/pkg-oss/raw-file/default/build_module.sh
$ chmod a+x build_module.sh
```

```
USAGE: build_module.sh [options] <URL | path to module source>

 URL may be Github clone or download link, otherwise 'tarball' is assumed.
 Options:
 -n | --nickname <word>         # Used for packaging, lower case alphanumeric only
 -s | --skip-depends            # Skip dependecies check/install
 -y | --non-interactive         # Automatically install dependencies and overwrite files
 -f | --force-dynamic           # Attempt to convert static configuration to dynamic module
 -r <NGINX Plus release number> # Build against the corresponding OSS version for this release
 -v [NGINX OSS version number]  # Build against this OSS version [current mainline] (default)
 -o <package output directory>  # Create package(s) in this directory
```

## ビルド
```
$ ./build_module.sh -f -v 1.14.0 https://github.com/YujiroTakahashi/ngx_hello_world.git
```

## パッケージのインストール

```
$ dpkg-deb -f ~/debuild/nginx-module-helloworld_1.14.0-1~bionic_amd64.deb
```


## 参考

[Creating Installable Packages for Dynamic Modules](https://www.nginx.com/blog/creating-installable-packages-dynamic-modules/)

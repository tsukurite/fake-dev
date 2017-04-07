# fake-dev

fake development env on nginx

## requirements

- [nginx](http://nginx.org/)
- [subs-filter-module](https://github.com/yaoweibin/ngx_http_substitutions_filter_module)

install from [Homebrew](http://brew.sh/):

```console
$ brew tap homebrew/nginx
$ brew install nginx-full --with-subs-filter-module
```

download config file:

```console
$ curl -L https://raw.githubusercontent.com/tsukurite/fake-dev/master/fake-dev.conf -o ~/.fake-dev.conf
```

## how to use

execute below:

```console
$ cd /path/to/app
$ nginx -p . -c ~/.fake-dev.conf
```

press `Ctrl-c` to exit.

## tips

easily execute with `fake-dev` alias:

```console
$ echo 'alias fake-dev="nginx -p . -c ~/.fake-dev.conf"' >> ~/.bashrc
```

```console
$ cd /path/to/app
$ fake-dev
```

## License

The MIT license. Please see top of `fake-dev.conf`.

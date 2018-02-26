# fake-dev

fake development environment with nginx

## requirements

- [nginx](http://nginx.org/)
- [subs-filter-module](https://github.com/yaoweibin/ngx_http_substitutions_filter_module)

install from [Homebrew](http://brew.sh/):

"homebrew/nginx" formulae renamed to "denji/homebrew"
```console
$ brew tap denji/nginx
$ brew install nginx-full --with-subs-filter-module
```

If the following error occurs ...
```console
# Error: Formulae found in multiple taps:
$ brew untap homebrew/nginx
$ brew tap denji/nginx
$ brew install nginx-full  --with-subs-filter-module
```

download config file:

```console
$ curl -L https://raw.githubusercontent.com/tsukurite/fake-dev/master/fake-dev.conf -o ~/.fake-dev.conf
```

## how to use

execute in `webroot` directory's hierarchy. execute below:

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

Start server with a specific port:
```console
cat << EOS >> ~/.bashrc
function fake-dev-port () {
  sed -e "s/127.0.0.1:8080/127.0.0.1:\$1/g" ~/.fake-dev.conf > ~/.fake-dev.temp.conf
  nginx -p . -c ~/.fake-dev.temp.conf
}
EOS
```


## License

The MIT license. Please see top of `fake-dev.conf`.

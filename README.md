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

## how to use

```console
$ cd /path/to/app
$ nginx -p . -c /path/to/fake-dev.conf
```

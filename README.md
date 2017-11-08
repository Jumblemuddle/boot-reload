# boot-reload [![Downloads](https://jarkeeper.com/adzerk/boot-reload/downloads.svg)](https://jarkeeper.com/adzerk/boot-reload) [![Build Status](https://travis-ci.org/adzerk-oss/boot-reload.svg?branch=master)](https://travis-ci.org/adzerk-oss/boot-reload) [![Dependencies Status](https://jarkeeper.com/adzerk/boot-reload/status.svg)](https://jarkeeper.com/adzerk/boot-reload)

[![Clojars Project][2]][3]

[Boot][1] task to automatically reload resources in the browser when files in
the project change. Communication with the client is via websockets.

* Provides the `reload` task
* Reload client can show warnings and exceptions **heads-up display**
    * Other tasks can use [this API](./doc/hud-messages.md) to send messages to Boot-reload
    * Supports [boot-cljs] (Requires `[adzerk/boot-cljs "1.7.48-5"]`)
    * Supports [less4clj] and [sass4clj]

## Usage

Add dependency to `build.boot` and `require` the task:

```clj
(set-env! :dependencies '[[adzerk/boot-reload "X.Y.Z" :scope "test"]])

(require '[adzerk.boot-reload :refer [reload]])
```

Add the task to your development pipeline **before `(cljs ...)`**:

```clj
(deftask dev []
  (comp
   (reload)
   (cljs)))
```

## Additional Info

You can see the options available on the command line:

```bash
boot reload --help
```

or in the REPL:

```clj
boot.user=> (doc reload)
```

## Examples

For in-depth, up-to-date examples of how to use `reload` in development, see
[Boot templates and example projects](https://github.com/clojure/clojurescript/wiki#boot)
in the ClojureScript wiki.

## License

Copyright &copy; 2014 Adzerk<br>
Copyright &copy; 2015-2017 Juho Teperi

Distributed under the Eclipse Public License either version 1.0 or (at
your option) any later version.

[1]:                https://github.com/boot-clj/boot
[2]:                http://clojars.org/adzerk/boot-reload/latest-version.svg?cache=6
[3]:                http://clojars.org/adzerk/boot-reload
[boot-cljs]: https://github.com/boot-clj/boot-cljs
[sass4clj]: https://github.com/Deraen/sass4clj
[less4clj]: https://github.com/Deraen/less4clj

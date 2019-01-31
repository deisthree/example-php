# PHP Quick Start Guide

This guide will walk you through deploying a PHP application on [Deis Workflow](https://github.com/teamhephy/workflow).

## Usage

```console
$ git clone https://github.com/teamhephy/example-php.git
$ cd example-php
$ deis create phptest
Creating Application... done, created phptest
Git remote deis added
remote available at ssh://git@deis-builder.deis.rocks:2222/phptest.git
$ deis config:set BUILDPACK_URL=https://github.com/heroku/heroku-buildpack-php
$ git push deis
Counting objects: 247, done.
Delta compression using up to 8 threads.
Compressing objects: 100% (176/176), done.
Writing objects: 100% (247/247), 376.76 KiB | 1.32 MiB/s, done.
Total 247 (delta 61), reused 247 (delta 61)
remote: Resolving deltas: 100% (61/61), done.
Starting build... but first, coffee!
-----> Restoring cache...
       No cache file found. If this is the first deploy, it will be created now.
-----> Fetching custom buildpack
-----> PHP app detected
-----> Bootstrapping...
-----> Installing platform packages...
       - php (7.3.1)
       - apache (2.4.37)
       - nginx (1.8.1)
-----> Installing dependencies...
       Composer version 1.8.0 2018-12-03 10:31:16
       Loading composer repositories with package information
       Installing dependencies from lock file
       Package operations: 5 installs, 0 updates, 0 removals
         - Installing psr/http-message (1.0.1): Downloading (100%)
         - Installing pimple/pimple (v3.0.2): Downloading (100%)
         - Installing nikic/fast-route (v1.0.1): Downloading (100%)
         - Installing container-interop/container-interop (1.1.0): Downloading (100%)
         - Installing slim/slim (3.5.0): Downloading (100%)
       Generating optimized autoload files
-----> Preparing runtime environment...
-----> Checking for additional extensions to install...
-----> Discovering process types
       Procfile declares types -> web
       Default process types for PHP -> web
-----> Checking for changes inside the cache directory...
       Files inside cache folder changed, uploading new cache...
       Done: Uploaded cache (232K)
-----> Compiled slug size is 16M
Build complete.->
Launching App...
...
...
...
Done, phptest:v3 deployed to Workflow

Use 'deis open' to view this application in your browser

To learn more, use 'deis help' or visit https://deis.com/

To ssh://deis-builder.deis.rocks:2222/phptest.git
 * [new branch]      master -> master
```

## Considerations

It is useful to specify which BuildPack must be used before deploying. 

```console
deis config:set BUILDPACK_URL=https://github.com/heroku/heroku-buildpack-php
```

## Additional Resources

* [GitHub Project](https://github.com/teamhephy/workflow)
* [Documentation](https://teamhephy.info/docs/workflow)
* [Blog](https://blog.teamhephy.info/)

[Deis Workflow]: https://github.com/deisthree/workflow#readme

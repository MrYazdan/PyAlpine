# Docker-PyAlpine
### Template of Python projects [Flask, Django, ...] using Docker on Alpine Linux 😋

<br>

### Simple Http Server :
>`docker-compose --env-file .env.info up` 


<br>


### Why Alpine linux ?
**Small, Simple, Secure** \
Alpine Linux is a security-oriented, lightweight Linux distribution based on musl libc and busybox.

+ **Small** \
Alpine Linux is built around musl libc and busybox. This makes it small and very resource efficient. A container requires no more than 8 MB and a minimal installation to disk requires around 130 MB of storage. Not only do you get a fully-fledged Linux environment but a large selection of packages from the repository. \
\
Binary packages are thinned out and split, giving you even more control over what you install, which in turn keeps your environment as small and efficient as possible.

+ **Simple** \
Alpine Linux is a very simple distribution that will try to stay out of your way. It uses its own package manager called apk, the OpenRC init system, script driven set-ups and that’s it! This provides you with a simple, crystal-clear Linux environment without all the noise. You can then add on top of that just the packages you need for your project, so whether it’s building a home PVR, or an iSCSI storage controller, a wafer-thin mail server container, or a rock-solid embedded switch, nothing else will get in the way.

+ **Secure** \
Alpine Linux was designed with security in mind. All userland binaries are compiled as Position Independent Executables (PIE) with stack smashing protection. These proactive security features prevent exploitation of entire classes of zero-day and other vulnerabilities.

<br>

### What's the difference with `python:3.10-alpine` ?
In this project, Docker files required for **Alpine Linux** and **Python** are included along with requirements such as ‍‍‍‍‍`gcc`, `libffi-dev`, `zlib-dev`, `musl-dev`, `postgresql-dev`, and `ca-certificates` etc.

<br>

### Examples:
+ **Go to *examples* directory for better understanding.**
  - [Django](/django)
  - [Flask](/flask)
  - [Sanic](/sanic)
  - [FastAPI](/fast-api)

# gcc10-alpine-package

_________

Republishing gcc 10.3.1 for Alpine Linux, for apps that (still) depend on it.

This repository is a copy and republish of the original `gcc-10.3.1` commit [(with hash `a2454e19ab90293b0d92b4515ad9e2c42b8a6d28`)](https://git.alpinelinux.org/aports/commit/?id=a2454e19ab90293b0d92b4515ad9e2c42b8a6d28), for Alpine Linux.

As Alpine is now distributing `gcc` 11+, this package may be useful to some.

Please always check your dependencies and which packages you need to fetch. The example below covers replacing `gcc-11.2.1_git20211128-r3` with this version; and requires three additional packages:

- `gcc-10.3.1`
- `libgomp-10.3.1`
- `libatomic-10.3.1`
- `libgphobos-10.3.1`

Here's the commands you can run in Alpine to fetch and replace your version of `gcc`:

```
apk --no-cache add ca-certificates wget
wget -q -O /etc/apk/keys/zalgonoise@gmail.com-61ca4660.rsa.pub https://raw.githubusercontent.com/ZalgoNoise/alpine-gcc10-package/master/zalgonoise%40gmail.com-61ca4660.rsa.pub
wget https://github.com/ZalgoNoise/gcc10-alpine-package/releases/download/gcc-10.3.1/linux_x86-64_gcc-10.3.1_git20210625-r0.apk 
wget https://github.com/ZalgoNoise/gcc10-alpine-package/releases/download/gcc-10.3.1/linux_x86-64_libgomp-10.3.1_git20210625-r0.apk 
wget https://github.com/ZalgoNoise/gcc10-alpine-package/releases/download/gcc-10.3.1/linux_x86-64_libatomic-10.3.1_git20210625-r0.apk 
wget https://github.com/ZalgoNoise/gcc10-alpine-package/releases/download/gcc-10.3.1/linux_x86-64_libgphobos-10.3.1_git20210625-r0.apk 
apk add \
    linux_x86-64_gcc-10.3.1_git20210625-r0.apk \
    linux_x86-64_libgomp-10.3.1_git20210625-r0.apk \
    linux_x86-64_libatomic-10.3.1_git20210625-r0.apk \
    linux_x86-64_libgphobos-10.3.1_git20210625-r0.apk 
```

If you intend to add it in a Dockerfile, add the snippet below:

```
ADD https://raw.githubusercontent.com/ZalgoNoise/alpine-gcc10-package/master/zalgonoise%40gmail.com-61ca4660.rsa.pub \
    /etc/apk/keys/zalgonoise@gmail.com-61ca4660.rsa.pub
ADD https://github.com/ZalgoNoise/gcc10-alpine-package/releases/download/gcc-10.3.1/linux_x86-64_gcc-10.3.1_git20210625-r0.apk \
    /tmp/gcc-10.3.1_git20210625-r0.apk
ADD https://github.com/ZalgoNoise/gcc10-alpine-package/releases/download/gcc-10.3.1/linux_x86-64_libgomp-10.3.1_git20210625-r0.apk \
    /tmp/libgomp-10.3.1_git20210625-r0.apk
ADD https://github.com/ZalgoNoise/gcc10-alpine-package/releases/download/gcc-10.3.1/linux_x86-64_libatomic-10.3.1_git20210625-r0.apk \
    /tmp/libatomic-10.3.1_git20210625-r0.apk
ADD https://github.com/ZalgoNoise/gcc10-alpine-package/releases/download/gcc-10.3.1/linux_x86-64_libgphobos-10.3.1_git20210625-r0.apk \
    /tmp/libgphobos-10.3.1_git20210625-r0.apk
RUN apk add \
    /tmp/gcc-10.3.1_git20210625-r0.apk \
    /tmp/libgomp-10.3.1_git20210625-r0.apk \
    /tmp/libatomic-10.3.1_git20210625-r0.apk \
    /tmp/libgphobos-10.3.1_git20210625-r0.apk 
```

_____________

Dockerfile reference for all packages:
```
ADD https://raw.githubusercontent.com/ZalgoNoise/alpine-gcc10-package/master/zalgonoise%40gmail.com-61ca4660.rsa.pub \
    /etc/apk/keys/zalgonoise@gmail.com-61ca4660.rsa.pub
ADD https://github.com/ZalgoNoise/gcc10-alpine-package/releases/download/gcc-10.3.1/linux_x86-64_libgcc-10.3.1_git20210625-r0.apk \ 
        /tmp/libgcc-10.3.1_git20210625-r0.apk
ADD https://github.com/ZalgoNoise/gcc10-alpine-package/releases/download/gcc-10.3.1/linux_x86-64_libgomp-10.3.1_git20210625-r0.apk \ 
        /tmp/libgomp-10.3.1_git20210625-r0.apk
ADD https://github.com/ZalgoNoise/gcc10-alpine-package/releases/download/gcc-10.3.1/linux_x86-64_libgfortran-10.3.1_git20210625-r0.apk \ 
        /tmp/libgfortran-10.3.1_git20210625-r0.apk
ADD https://github.com/ZalgoNoise/gcc10-alpine-package/releases/download/gcc-10.3.1/linux_x86-64_g++-10.3.1_git20210625-r0.apk \ 
        /tmp/g++-10.3.1_git20210625-r0.apk
ADD https://github.com/ZalgoNoise/gcc10-alpine-package/releases/download/gcc-10.3.1/linux_x86-64_gfortran-10.3.1_git20210625-r0.apk \ 
        /tmp/gfortran-10.3.1_git20210625-r0.apk
ADD https://github.com/ZalgoNoise/gcc10-alpine-package/releases/download/gcc-10.3.1/linux_x86-64_libgnat-10.3.1_git20210625-r0.apk \ 
        /tmp/libgnat-10.3.1_git20210625-r0.apk
ADD https://github.com/ZalgoNoise/gcc10-alpine-package/releases/download/gcc-10.3.1/linux_x86-64_libgo-10.3.1_git20210625-r0.apk \ 
        /tmp/libgo-10.3.1_git20210625-r0.apk
ADD https://github.com/ZalgoNoise/gcc10-alpine-package/releases/download/gcc-10.3.1/linux_x86-64_gcc-objc-10.3.1_git20210625-r0.apk \ 
        /tmp/gcc-objc-10.3.1_git20210625-r0.apk
ADD https://github.com/ZalgoNoise/gcc10-alpine-package/releases/download/gcc-10.3.1/linux_x86-64_libgphobos-10.3.1_git20210625-r0.apk \ 
        /tmp/libgphobos-10.3.1_git20210625-r0.apk
ADD https://github.com/ZalgoNoise/gcc10-alpine-package/releases/download/gcc-10.3.1/linux_x86-64_libquadmath-10.3.1_git20210625-r0.apk \ 
        /tmp/libquadmath-10.3.1_git20210625-r0.apk
ADD https://github.com/ZalgoNoise/gcc10-alpine-package/releases/download/gcc-10.3.1/linux_x86-64_gcc-gdc-10.3.1_git20210625-r0.apk \ 
        /tmp/gcc-gdc-10.3.1_git20210625-r0.apk
ADD https://github.com/ZalgoNoise/gcc10-alpine-package/releases/download/gcc-10.3.1/linux_x86-64_gcc-go-10.3.1_git20210625-r0.apk \ 
        /tmp/gcc-go-10.3.1_git20210625-r0.apk
ADD https://github.com/ZalgoNoise/gcc10-alpine-package/releases/download/gcc-10.3.1/linux_x86-64_gcc-10.3.1_git20210625-r0.apk \ 
        /tmp/gcc-10.3.1_git20210625-r0.apk
ADD https://github.com/ZalgoNoise/gcc10-alpine-package/releases/download/gcc-10.3.1/linux_x86-64_libobjc-10.3.1_git20210625-r0.apk \ 
        /tmp/libobjc-10.3.1_git20210625-r0.apk
ADD https://github.com/ZalgoNoise/gcc10-alpine-package/releases/download/gcc-10.3.1/linux_x86-64_libatomic-10.3.1_git20210625-r0.apk \ 
        /tmp/libatomic-10.3.1_git20210625-r0.apk
ADD https://github.com/ZalgoNoise/gcc10-alpine-package/releases/download/gcc-10.3.1/linux_x86-64_libgnat-static-10.3.1_git20210625-r0.apk \ 
        /tmp/libgnat-static-10.3.1_git20210625-r0.apk
ADD https://github.com/ZalgoNoise/gcc10-alpine-package/releases/download/gcc-10.3.1/linux_x86-64_gcc-gnat-10.3.1_git20210625-r0.apk \ 
        /tmp/gcc-gnat-10.3.1_git20210625-r0.apk
ADD https://github.com/ZalgoNoise/gcc10-alpine-package/releases/download/gcc-10.3.1/linux_x86-64_gcc-doc-10.3.1_git20210625-r0.apk \ 
        /tmp/gcc-doc-10.3.1_git20210625-r0.apk
ADD https://github.com/ZalgoNoise/gcc10-alpine-package/releases/download/gcc-10.3.1/linux_x86-64_libstdc++-10.3.1_git20210625-r0.apk \ 
        /tmp/libstdc++-10.3.1_git20210625-r0.apk
WORKDIR /tmp
RUN apk add * && rm -rf * 
```

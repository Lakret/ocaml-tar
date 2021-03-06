## tar -- decode and encode tar files

tar is a simple library to read and write tar files with an emphasis on
streaming.

This is pure OCaml code, no C bindings.

## Example toplevel session

In utop:
```
utop # #require "tar";;
utop # #require "tar.lwt";;

utop # lwt f = Lwt_unix.openfile "/tmp/foo.tar" [ Unix.O_RDONLY ] 0 ;;
val f : Lwt_unix.file_descr = <abstr> 

utop # Tar_lwt_unix.Archive.list f;;
[{Tar_lwt_unix.Header.file_name = "_build/lib/tar.mli.depends";
  Tar_lwt_unix.Header.file_mode = 420; Tar_lwt_unix.Header.user_id = 1000;
  Tar_lwt_unix.Header.group_id = 1000; Tar_lwt_unix.Header.file_size = 21L;
  Tar_lwt_unix.Header.mod_time = 1381080315L;
  Tar_lwt_unix.Header.link_indicator = Tar_lwt_unix.Header.Link.Normal;
  Tar_lwt_unix.Header.link_name = ""};
 {Tar_lwt_unix.Header.file_name = "_build/lib/tar_unix.mli.depends";
  Tar_lwt_unix.Header.file_mode = 420; Tar_lwt_unix.Header.user_id = 1000;
  Tar_lwt_unix.Header.group_id = 1000; Tar_lwt_unix.Header.file_size = 27L;
  Tar_lwt_unix.Header.mod_time = 1381080318L;
  Tar_lwt_unix.Header.link_indicator = Tar_lwt_unix.Header.Link.Normal;
  Tar_lwt_unix.Header.link_name = ""};
 {Tar_lwt_unix.Header.file_name = "_build/lib/tar.mllib";
  Tar_lwt_unix.Header.file_mode = ...; Tar_lwt_unix.Header.user_id = ...;
  Tar_lwt_unix.Header.group_id = ...; Tar_lwt_unix.Header.file_size = ...;
  Tar_lwt_unix.Header.mod_time = ...; Tar_lwt_unix.Header.link_indicator = ...;
  Tar_lwt_unix.Header.link_name = ...};
 ...]
```

## Example users

This library is used by
* [xapi](https://www.github.com/xapi-project/xen-api) to read and write VM images

## Installation

`tar` can be installed with `opam`:

    opam install tar

If you don't use `opam` consult the [`tar.opam`](tar.opam) file for build
instructions.

### Documentation

[![Build Status](https://travis-ci.org/mirage/ocaml-tar.svg?branch=master)](https://travis-ci.org/mirage/ocaml-tar)

The documentation and API reference is automatically generated by
`ocamldoc` from the interfaces. It can be consulted [online][2].

[2]: https://mirage.github.io/ocaml-tar/Tar.html


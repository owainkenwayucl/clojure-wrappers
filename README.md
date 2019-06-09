# Clojure wrappers

By default Clojure has a fairly terrible wrapper to make it behave like a language with a REPL but no compiler.  This situation is made even more confusing by the fact that the Debian and Ubuntu packages come with their own wrappers, `clojure` and `clojurec` which start a REPL and a stand-alone compiler respectively.

This project aims to produce portable wrappers to do the same.

These are:

`clojure-repl` - Wrapper to launch a REPL.

```none
usage: clojure-repl [-h] [-cp classpath] [-mem JVM memory]

Clojure REPL

optional arguments:
  -h, --help       show this help message and exit
  -cp classpath    Set CLASSPATH.
  -mem JVM memory  Set JVM memory.
```

`clojure-compiler` - Wrapper to launch the compiler.

```none
usage: clojure-compiler [-h] [-cp classpath] [-warn] [-mem JVM memory]
                        [-dir Destination directory]

Clojure Compiler

optional arguments:
  -h, --help            show this help message and exit
  -cp classpath         Set CLASSPATH.
  -warn                 Enable reflection warnings.
  -mem JVM memory       Set JVM memory.
  -dir Destination directory
                        Set destination directory.
```

The wrappers can be configured by editing `clojure-wrappers.ini` to set the`CLASSPATH` and `rlwrap` options appropriately.  By default it's set up appropriately for Ubuntu 18.04's Clojure package.

```none
[clojure]
classpath: /usr/share/java/clojure-1.9.jar
rlwrap: rlwrap -c -C clojure
```
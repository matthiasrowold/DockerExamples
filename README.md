# DockerExamples
Minimal examples to learn docker

## Run a container with interface to the terminal:
https://docs.docker.com/engine/reference/run/

E.g. with the python image:
```python
docker run -a=stdin -a=stdout -i -t python:3.7
```
Option              | Meaning
--------------------| ------------------------
-a=[]               | Attach to `STDIN`, `STDOUT` and/or `STDERR`
-t                  | Allocate a pseudo-tty
--sig-proxy=true    | Proxy all received signals to the process (non-TTY mode only)
-i                  | Keep STDIN open even if not attached

If the container should run in the background add the option `-d` and the current terminal is not attached to stdin, stdout or stderr of the process.

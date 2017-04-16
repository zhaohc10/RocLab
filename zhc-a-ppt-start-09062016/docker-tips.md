### ENTRYPOINT vs CMD
When both an ENTRYPOINT and CMD are specified, 
the CMD string(s) will be appended to the ENTRYPOINT in order to generate the container's command string. 
```
FROM ubuntu:trusty
ENTRYPOINT ["/bin/ping","-c","3"]
CMD ["localhost"]
```
>When using ENTRYPOINT and CMD together it's important that you always use the exec form of both instructions.
A better option is to use the exec form of the ENTRYPOINT/CMD instructions which looks like this:
```
CMD ["executable","param1","param2"]
```

The default ENTRYPOINT can be overridden use of the --entrypoint flag:
```
docker run --entrypoint <hostname> <demo>
```
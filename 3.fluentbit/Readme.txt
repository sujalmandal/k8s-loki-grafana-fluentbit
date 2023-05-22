When running kubernetes in windows desktop docker
-----------------------------------------------------------------------------
docker run -it --privileged --pid=host debian nsenter -t 1 -m -u -n -i sh
-----------------------------------------------------------------------------
to drop into the VM where docker runs the containers.

This VM is effectively the kubernetes node.
All the pods that run in this VM/Node will write their stdout, stderr logs to "/var/log/containers".

Any daemonset that runs in this node should be able to read the files here.




-------------------------------------------------------
enrich logs with kubernetes metadata
-------------------------------------------------------
https://docs.fluentbit.io/manual/pipeline/filters/kubernetes
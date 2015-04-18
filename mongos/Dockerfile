from varunmittal91/mongod:latest

ENTRYPOINT ["/usr/bin/numactl", "--interleave", "all",  "/usr/bin/mongos", "--port", "27017", "--logpath", "/data/log", "--quiet"]

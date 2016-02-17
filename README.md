# OpenShift typesafe activator Cartridge

## Use it

In OpenShift, choose a downloaded cartridge, with the following URL : http://cartreflect-claytondev.rhcloud.com/reflect?github=mhashimm/openshift-cartridge-scala

On git push, `./activator compile` will be called, then the script `start.sh` at the root of your repo will be called.

Example of `start.sh` script:

    #!/bin/bash
    ./activator run

Make sure `start.sh` is an executable file: `chmod +x start.sh`

In your application listen on the environment variable $OPENSHIFT_SCALA_IP:$OPENSHIFT_SCALA_PORT

    interface = System.getenv("OPENSHIFT_SCALA_IP")
    port = System.getenv("OPENSHIFT_SCALA_PORT").toInt

This cartidge embed an akka example, but you could use any framework as long as activator is used for compilation.

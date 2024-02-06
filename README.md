Installation of ocp logging

First we need to install the logging operator into our openshift cluster, for that we mus log into it with the CLI and then apply the files hosted in the logging-operator folder with the command 
$ oc apply -f <filename>.yaml

After that we need to create the ClusterLogging object

We create the ClusterForwarder:
  - we create a secret with our Base64 encoded Splunk HEC token:
    
    $ oc -n openshift-logging create secret generic vector-splunk-secret --from-literal hecToken=<HEC_Token>
    
  - we create the object

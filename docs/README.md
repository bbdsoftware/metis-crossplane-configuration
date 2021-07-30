# Crossplane custom Configuration for bootstrapping clusters

The custom configuration install various xrds that can be used to bootstrap clusters in an opinioated fashion.

# Install 

### Crossplane
- Ensure Crossplane is installed please follow instructions at [crossplane](https://crossplane.github.io/docs/v1.0/getting-started/install-configure.html)


## Build and publis
- Ensure the crossplane cli is installed from https://crossplane.io/docs/v1.3/getting-started/install-configure.html#install-crossplane-cli
 
### Make
  The provided make file will run the crossplane build and publish command to publish the configuration as an OCI image


### Install configuration into a cluster
   Applying the following configuration will install the configuration into your cluster

```
    apiVersion: pkg.crossplane.io/v1
    kind: Configuration
    metadata:
      name: platfrom-bootstrap
    spec:
      package: kanzifucius/metis-crossplane-configuration:master
      packagePullPolicy: Always
      revisionActivationPolicy: Automatic
      revisionHistoryLimit: 1
  ```

# Usage
  See manifests in bootstrap-examples [examples](../examples)


  
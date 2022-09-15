# Mongodb template

Run mongodb on the Red Hat OpenShift platform v4.  This package is based on [bitnami images](https://hub.docker.com/r/bitnami/mongodb).

MongoDB will be only accesible from inside the namespace at `mongdb:27017`. MongoDB will store the data in a dedicated Persisten Volume.

## How to deploy this template

Install the template by downloading the [mongodb-template.yaml](./mongodb-template.yaml) file and import it to your OpenShift project via command line. Download the `oc` client [here](https://docs.openshift.com/container-platform/4.7/cli_reference/openshift_cli/getting-started-cli.html). Then:

```sh
oc login "openshift-address" --token="<TOKEN>"
oc new-project "<project-name>"
```

**NOTE:** Replace `<TOKEN>` by the corresponding value

Process and apply template using default values from the template and passing your application specific parameters.

```sh
oc process -f wordpress-template.yaml | oc apply -f -
```

By default version `6.0` is deployed. For a whole list of versions available, visit the [docker hub page](https://hub.docker.com/r/bitnami/mongodb/tags) with all the tags available.

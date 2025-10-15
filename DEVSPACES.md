# OpenShift DevSpaces

1. Install OpenShift DevSpaces operator.

2. Create devspaces namespace
```bash
oc create ns openshift-devspaces
```

3. In the operator, create a **CheCluster**. In the yaml view, change namespace to *openshift-devspaces*.

4. When ready, open the DevSpaces URL from Operator CheCluster view and login via OpenShift.

5. Create Workspace with the git repo and config:
https://github.com/nikolaus-lemberski/hello-spring-native?memoryLimit=6Gi&devfilePath=dev%2Fdevfile.yaml

6. In the Workspaces IDE, create a new terminal (select container) and the tooling container will be used (see dev/devfile.yaml). Then you can compile native
```bash
$ ./mvnw spring-boot:build-image -Pnative
```
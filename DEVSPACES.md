# OpenShift DevSpaces

1. Install OpenShift DevSpaces operator.

2. Create devspaces namespace
```bash
oc create ns openshift-devspaces
```

3. In the operator, create a **CheCluster**. In the yaml view, change namespace to *openshift-devspaces*.

4. When ready, open the DevSpaces URL from Operator CheCluster view and login via OpenShift.

5. Create Workspace with the git repo and config:  
https://github.com/nikolaus-lemberski/hello-spring-native?memoryLimit=8Gi&devfilePath=dev%2Fdevfile.yaml

6. Install GraalVM

In the Workspaces IDE, create a new terminal (select container) and the tooling container will be used (see *dev/devfile.yaml*).

Use the preinstalled *sdkman* to install *GraalVM*:

```bash
sdk list java
```

Select a GraalVM version (for example *25-graalce*) and run:

```bash
sdk install java 25-graalce
```

Then, set the GRAALVM_HOME to that version (maybe run `echo $GRAALVM_HOME` to find the current path):

```bash
GRAALVM_HOME=/home/tooling/.sdkman/candidates/java/25-graalce
```

Now you can compile native with

```bash
./mvnw native:compile -Pnative
```
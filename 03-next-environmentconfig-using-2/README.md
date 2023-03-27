```bash
kubectl get managed 

NAME                                                        READY   SYNCED   ID                         VPC                     CIDR            AGE
subnet.ec2.aws.crossplane.io/environment-test-kswmv-fz555   True    True     subnet-0b795de7f690090f3   vpc-0ae1bef8fc2a335a1   172.16.0.0/16   78s

NAME                                                     READY   SYNCED   ID                      CIDR            IPV6CIDR   AGE
vpc.ec2.aws.crossplane.io/environment-test-kswmv-frcfd   True    True     vpc-0ae1bef8fc2a335a1   172.16.0.0/16              79s
```

```bash
kubectl get EnvironmentConfig -o yaml
apiVersion: v1
items:
- apiVersion: apiextensions.crossplane.io/v1alpha1
  data:
    bool: false
    cidrBlock: 172.16.0.0/16
    complex:
      a: b
      c:
        d: e
    int: 123
    list:
    - a
    - b
    - c
    region: us-west-1
    simple: value
  kind: EnvironmentConfig
  metadata:
    annotations:
      crossplane.io/composition-resource-name: env
      kubectl.kubernetes.io/last-applied-configuration: |
        {"apiVersion":"apiextensions.crossplane.io/v1alpha1","data":{"bool":false,"complex":{"a":"b","c":{"d":"e"}},"int":123,"list":["a","b","c"],"region":"us-west-1","simple":"value"},"kind":"EnvironmentConfig","metadata":{"annotations":{},"name":"example-environment"}}
    creationTimestamp: "2023-03-27T11:23:22Z"
    generateName: environment-test-kswmv-
    generation: 2
    labels:
      crossplane.io/claim-name: environment-test
      crossplane.io/claim-namespace: default
      crossplane.io/composite: environment-test-kswmv
    name: example-environment
    ownerReferences:
    - apiVersion: example.crossplane.io/v1alpha1
      blockOwnerDeletion: true
      controller: true
      kind: XEnvironmentSample
      name: environment-test-kswmv
      uid: 48d1669e-9994-4fd2-b601-4e190d3fa6ea
    resourceVersion: "10225"
    uid: 625c36e6-a5cf-4832-853c-886fea8fb101
kind: List
metadata:
  resourceVersion: ""

```
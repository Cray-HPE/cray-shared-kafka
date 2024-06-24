# cray-shared-kafka

### Description
cray-shared-kafka holds the helm charts for creating the custom resources(kafka/zookeeper/kafkatopics) needed for setting up kafka. These resources are created in services namespace.
Changes are also needed in another repository that works in tandem with this one - [cray-kafka-operator](#https://github.com/Cray-HPE/cray-kafka-operator)

### Prerequisites
1. As part of upgrading to a new version, make sure the latest version images are added to artifactory. 
This can be done as part of [container-images](#https://github.com/Cray-HPE/container-images)
2. These charts can be deployed only after the operator and needed CRDs are deployed that are done as part of cray-kafka-operator. 
   
### Installation
Once the changes are done, the helm charts are added to artifactory in unstable directory if commits are made to the development branch (or) in stable directory once the changes are merged to master branch.
These charts can be deployed on a cluster using standard helm commands - 
```text
helm upgrade --install <release-name> <chart> -n <namespace>
```
As an example,
```text
helm upgrade --install cray-shared-kafka cray-shared-kafka-1.0.0.tgz -n services 
```

### Contributing
See the [CONTRIBUTING.md](/CONTRIBUTING.md) file for how to contribute to this project.

### License
This project is copyrighted by Hewlett Packard Enterprise Development LP and is distributed under the MIT license. See the [LICENSE](/LICENSE) file for details.

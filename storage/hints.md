Installing the AWS CSI driver for EFS
https://catalog.us-east-1.prod.workshops.aws/workshops/76a5dd80-3249-4101-8726-9be3eeee09b2/en-US/persistentstorage-efs/efs-csi-driver

Example manifest to configure Storage Class, PV and PV Claim
https://www.eksworkshop.com/beginner/190_efs/efs.files/efs-pvc.yaml

Git Repo for AWS EBS CSI driver
https://github.com/kubernetes-sigs/aws-ebs-csi-driver/tree/master/examples/kubernetes


## CSI Driver Install

>helm repo add aws-efs-csi-driver https://kubernetes-sigs.github.io/aws-efs-csi-driver/
>helm repo add aws-ebs-csi-driver https://kubernetes-sigs.github.io/aws-ebs-csi-driver/

>helm repo update

>helm upgrade --install aws-efs-csi-driver --namespace kube-system aws-efs-csi-driver/aws-efs-csi-driver

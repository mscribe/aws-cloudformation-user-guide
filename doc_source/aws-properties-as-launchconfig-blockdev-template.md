# AWS::AutoScaling::LaunchConfiguration BlockDevice<a name="aws-properties-as-launchconfig-blockdev-template"></a>

 `BlockDevice` is a subproperty of [BlockDeviceMapping](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-as-launchconfig-blockdev-mapping.html) that describes an Amazon EBS volume\.

For Amazon EC2 Auto Scaling EBS Block Device snippets, see [Auto Scaling Launch Configuration Resource](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/quickref-autoscaling.html#scenario-as-launch-config)\. 

## Syntax<a name="aws-properties-as-launchconfig-blockdev-template-syntax"></a>

To declare this entity in your AWS CloudFormation template, use the following syntax:

### JSON<a name="aws-properties-as-launchconfig-blockdev-template-syntax.json"></a>

```
{
  "[DeleteOnTermination](#cfn-as-launchconfig-blockdev-template-deleteonterm)" : Boolean,
  "[Encrypted](#cfn-as-launchconfig-blockdev-template-encrypted)" : Boolean,
  "[Iops](#cfn-as-launchconfig-blockdev-template-iops)" : Integer,
  "[SnapshotId](#cfn-as-launchconfig-blockdev-template-snapshotid)" : String,
  "[VolumeSize](#cfn-as-launchconfig-blockdev-template-volumesize)" : Integer,
  "[VolumeType](#cfn-as-launchconfig-blockdev-template-volumetype)" : String
}
```

### YAML<a name="aws-properties-as-launchconfig-blockdev-template-syntax.yaml"></a>

```
﻿  [DeleteOnTermination](#cfn-as-launchconfig-blockdev-template-deleteonterm) : Boolean
﻿  [Encrypted](#cfn-as-launchconfig-blockdev-template-encrypted) : Boolean
﻿  [Iops](#cfn-as-launchconfig-blockdev-template-iops) : Integer
﻿  [SnapshotId](#cfn-as-launchconfig-blockdev-template-snapshotid) : String
﻿  [VolumeSize](#cfn-as-launchconfig-blockdev-template-volumesize) : Integer
﻿  [VolumeType](#cfn-as-launchconfig-blockdev-template-volumetype) : String
```

## Properties<a name="aws-properties-as-launchconfig-blockdev-template-properties"></a>

`DeleteOnTermination`  <a name="cfn-as-launchconfig-blockdev-template-deleteonterm"></a>
Indicates whether to delete the volume when the instance is terminated\. For Amazon EC2 Auto Scaling, the default value is `true`\.   
*Required*: No  
*Type*: Boolean  
*Update requires*: [No interruption](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-update-behaviors.html#update-no-interrupt)

`Encrypted`  <a name="cfn-as-launchconfig-blockdev-template-encrypted"></a>
Specifies whether the volume should be encrypted\. Encrypted EBS volumes must be attached to instances that support Amazon EBS encryption\. Volumes that are created from encrypted snapshots are automatically encrypted\. You cannot create an encrypted volume from an unencrypted snapshot or an unencrypted volume from an encrypted snapshot\. If your AMI uses encrypted volumes, you can only launch it on supported instance types\. For more information, see [Amazon EBS Encryption](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSEncryption.html) in the *Amazon EC2 User Guide for Linux Instances*\.  
*Required*: No  
*Type*: Boolean  
*Update requires*: [No interruption](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-update-behaviors.html#update-no-interrupt)

`Iops`  <a name="cfn-as-launchconfig-blockdev-template-iops"></a>
The number of I/O operations per second \(IOPS\) to provision for the volume\. The maximum ratio of IOPS to volume size \(in GiB\) is 50:1\. For more information, see [Amazon EBS Volume Types](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSVolumeTypes.html) in the *Amazon EC2 User Guide for Linux Instances*\.  
If the volume type is `io1`, this property is required\. \(Not used with `standard`, `gp2`, `st1`, or `sc1` volumes\.\)   
*Required*: Conditional  
*Type*: Integer  
*Minimum*: `100`  
*Maximum*: `20000`  
*Update requires*: [No interruption](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-update-behaviors.html#update-no-interrupt)

`SnapshotId`  <a name="cfn-as-launchconfig-blockdev-template-snapshotid"></a>
The snapshot ID of the volume to use\.   
You must specify either a `VolumeSize` or a `SnapshotId`\.   
*Required*: Conditional  
*Type*: String  
*Minimum*: `1`  
*Maximum*: `255`  
*Pattern*: `[\u0020-\uD7FF\uE000-\uFFFD\uD800\uDC00-\uDBFF\uDFFF\r\n\t]*`  
*Update requires*: [No interruption](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-update-behaviors.html#update-no-interrupt)

`VolumeSize`  <a name="cfn-as-launchconfig-blockdev-template-volumesize"></a>
The volume size, in Gibibytes \(GiB\)\.   
This can be a number from 1\-1,024 for `standard`, 4\-16,384 for `io1`, 1\-16,384 for `gp2`, and 500\-16,384 for `st1` and `sc1`\. If you specify a snapshot, the volume size must be equal to or larger than the snapshot size\. If the volume type is EBS optimized, the minimum value is 10\.  For information about specifying EBS\-optimized volumes, see [AWS::AutoScaling::LaunchConfiguration](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-as-launchconfig.html)\.  
If you create a volume from a snapshot and you don't specify a volume size, the default is the snapshot size\.   
You must specify either a `VolumeSize` or a `SnapshotId`\. If you specify both `SnapshotId` and `VolumeSize`, `VolumeSize` must be equal or greater than the size of the snapshot\.  
*Required*: Conditional  
*Type*: Integer  
*Minimum*: `1`  
*Maximum*: `16384`  
*Update requires*: [No interruption](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-update-behaviors.html#update-no-interrupt)

`VolumeType`  <a name="cfn-as-launchconfig-blockdev-template-volumetype"></a>
The volume type, which can be `standard` for Magnetic, `io1` for Provisioned IOPS SSD, `gp2` for General Purpose SSD, `st1` for Throughput Optimized HDD, or `sc1` for Cold HDD\. For more information, see [Amazon EBS Volume Types](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSVolumeTypes.html) in the *Amazon EC2 User Guide for Linux Instances*\.  
Valid values: `standard` \| `io1` \| `gp2` \| `st1` \| `sc1`   
*Required*: No  
*Type*: String  
*Minimum*: `1`  
*Maximum*: `255`  
*Update requires*: [No interruption](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-update-behaviors.html#update-no-interrupt)
---
UID: NS:wdm._CLFS_MGMT_POLICY
title: "_CLFS_MGMT_POLICY"
description: The CLFS_MGMT_POLICY structure holds a description of a policy for managing a CLFS log.
old-location: kernel\clfs_mgmt_policy.htm
tech.root: kernel
ms.assetid: 6765ced9-e21f-4bd9-bb2b-45df1d6dba75
ms.date: 04/30/2018
ms.keywords: "*PCLFS_MGMT_POLICY, CLFS_MGMT_POLICY, CLFS_MGMT_POLICY structure [Kernel-Mode Driver Architecture], PCLFS_MGMT_POLICY, PCLFS_MGMT_POLICY structure pointer [Kernel-Mode Driver Architecture], _CLFS_MGMT_POLICY, kernel.clfs_mgmt_policy, kstruct_a_12bfc6be-5318-49df-b74a-251c40c0b916.xml, wdm/CLFS_MGMT_POLICY, wdm/PCLFS_MGMT_POLICY"
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	CLFS_MGMT_POLICY
product:
- Windows
targetos: Windows
req.typenames: CLFS_MGMT_POLICY, *PCLFS_MGMT_POLICY
---

# _CLFS_MGMT_POLICY structure


## -description


The <b>CLFS_MGMT_POLICY</b> structure holds a description of a policy for managing a CLFS log.


## -struct-fields




### -field Version

The version of the <b>CLFS_MGMT_POLICY</b> structure. Set this to <b>CLFS_MGMT_POLICY_VERSION</b>.


### -field LengthInBytes

The length of the <b>CLFS_MGMT_POLICY</b> structure.


### -field PolicyFlags

The flags that apply to this instance of the <b>CLFS_MGMT_POLICY</b> structure. The only flag that has been implemented for this release is <b>LOG_POLICY_OVERWRITE</b>, which indicates that when the policy is installed, it will replace the policy of the same type, if such a policy already exists.


### -field PolicyType

A value of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541849">CLFS_MGMT_POLICY_TYPE</a> enumeration that supplies the type of this instance of the <b>CLFS_MGMT_POLICY</b> structure.


### -field PolicyParameters

The union that provides the detailed information about this instance of the <b>CLFS_MGMT_POLICY</b> structure.


### -field PolicyParameters.MaximumSize

The structure that provides the detailed information about a policy whose <b>PolicyType</b> is <b>ClfsMgmtPolicyMaximumSize</b>.


### -field PolicyParameters.MaximumSize.Containers

The maximum number of containers that the log will use.


### -field PolicyParameters.MinimumSize

The structure that provides the detailed information about a policy whose <b>PolicyType</b> is <b>ClfsMgmtPolicyMinimumSize</b>.


### -field PolicyParameters.MinimumSize.Containers

The minimum number of containers that the log will use.


### -field PolicyParameters.NewContainerSize

The structure that provides the detailed information about a policy whose <b>PolicyType</b> is <b>ClfsMgmtPolicyNewContainerSize</b>.


### -field PolicyParameters.NewContainerSize.SizeInBytes

The size of each of the log's containers.


### -field PolicyParameters.GrowthRate

The structure that provides the detailed information about a policy whose <b>PolicyType</b> is <b>ClfsMgmtPolicyGrowthRate</b>.


### -field PolicyParameters.GrowthRate.AbsoluteGrowthInContainers

The number of containers that should be added when the size of the log is increased. If the <b>RelativeGrowthPercentage</b> member is nonzero, then <b>AbsoluteGrowthInContainers</b> must be zero.


### -field PolicyParameters.GrowthRate.RelativeGrowthPercentage

The percentage by which the log's size should increase when the log grows, expressed as a number between zero and 100. For example, if the log consisted of 32 containers and <b>RelativeGrowthPercentage</b> was ten, then, when the log needed to grow, it would grow by three (32 * 10 percent, rounded down to the nearest integer) containers. If the <b>AbsoluteGrowthInContainers</b> member is nonzero, then <b>RelativeGrowthPercentage</b> must be zero.


### -field PolicyParameters.LogTail

The structure that provides the detailed information about a policy whose <b>PolicyType</b> is <b>ClfsMgmtPolicyLogTail</b>.


### -field PolicyParameters.LogTail.MinimumAvailablePercentage

When CLFS management notifies the client to move its log tail, it will specify that the tail be moved to an LSN that leaves at least <b>MinimumAvailablePercentage</b> percent of the log free. If the <b>MinimumAvailableContainers</b> member is nonzero, then <b>MinimumAvailablePercentage</b> must be zero.


### -field PolicyParameters.LogTail.MinimumAvailableContainers

When CLFS management notifies the client to move its log tail, it will specify that the tail be moved to an LSN that leaves at least <b>MinimumAvailableContainers</b> containers free. If the <b>MinimumAvailablePercentage</b> member is nonzero, then <b>MinimumAvailableContainers</b> must be zero.


### -field PolicyParameters.AutoShrink

The structure that provides the detailed information about a policy whose <b>PolicyType</b> is <b>ClfsMgmtPolicyAutoShrink</b>.


### -field PolicyParameters.AutoShrink.Percentage

When the percentage of free space in the log reaches <b>Percentage</b>, the log will shrink. Percentage is expressed as a number between 0 and 100, so a value of 25 would mean 25 percent.


### -field PolicyParameters.AutoGrow

The structure that provides the detailed information about a policy whose <b>PolicyType</b> is <b>ClfsMgmtPolicyAutoGrow</b>.


### -field PolicyParameters.AutoGrow.Enabled

A numeric value that determines whether automatic log growth is enabled. Any nonzero value enables automatic growth.


### -field PolicyParameters.NewContainerPrefix

The structure that provides the detailed information about a policy whose <b>PolicyType</b> is <b>ClfsMgmtPolicyNewContainerPrefix</b>.


### -field PolicyParameters.NewContainerPrefix.PrefixLengthInBytes

The length, in bytes, of the <b>PrefixString</b> member.


### -field PolicyParameters.NewContainerPrefix.PrefixString

A wide-character string that contains the full path to the directory where the log's containers reside, as well as a prefix that will be used as part of the file name for each container in the log.


### -field PolicyParameters.NewContainerSuffix

The structure that provides the detailed information about a policy whose <b>PolicyType</b> is <b>ClfsMgmtPolicyNewContainerSuffix</b>.


### -field PolicyParameters.NewContainerSuffix.NextContainerSuffix

The number to use as the suffix of the file name for the next container in the log. To form the file name, the number is converted to a string of decimal digits and appended to the prefix string. The number is incremented for the file name of each subsequent container.


### -field PolicyParameters.NewContainerExtension

The structure that provides the detailed information about a policy whose <b>PolicyType</b> is <b>ClfsMgmtPolicyNewContainerExtension</b>.


### -field PolicyParameters.NewContainerExtension.ExtensionLengthInBytes

The length, in bytes, of the <b>ExtensionString</b> member.


### -field PolicyParameters.NewContainerExtension.ExtensionString

A wide-character string that contains the extension to the file name for each container in the log. Container file names are built using the format [prefix][suffix][.extension]. An extension is optional. The default extension is the empty string.


## -remarks



The way a <b>CLFS_MGMT_POLICY</b> structure is interpreted depends on the type of policy that the structure holds.

You can provide <i>policies</i> that specify how the log will be managed. Each policy is an instance of the <b>CLFS_MGMT_POLICY</b> structure, but the structure is interpreted differently depending on the policy type. CLFS uses the information that you provided in the policies to tailor how it manages the log.

When you create a <b>CLFS_MGMT_POLICY</b> structure whose <b>PolicyType</b> is <b>ClfsMgmtPolicyNewContainerPrefix</b>, be sure to allocate enough space to hold the <b>PolicyParameters.NewContainerPrefix.PrefixString</b> string.

You can only install a policy whose policy type specified in the <b>PolicyType</b> value is <b>ClfsMgmtPolicyNewContainerSize</b> before there are any containers in the log. You can change other policies after the log exists.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541849">CLFS_MGMT_POLICY_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541634">ClfsMgmtInstallPolicy</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541638">ClfsMgmtQueryPolicy</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541648">ClfsMgmtRemovePolicy</a>
 

 


---
UID: NE:wdm._CLFS_MGMT_POLICY_TYPE
title: _CLFS_MGMT_POLICY_TYPE (wdm.h)
description: The CLFS_MGMT_POLICY_TYPE enumeration type identifies the type of a CLFS management policy.
old-location: kernel\clfs_mgmt_policy_type.htm
tech.root: kernel
ms.assetid: 50e31ff1-07f2-4781-81f2-8db6e3cf9cc6
ms.date: 04/30/2018
keywords: ["_CLFS_MGMT_POLICY_TYPE enumeration"]
ms.keywords: "*PCLFS_MGMT_POLICY_TYPE, CLFS_MGMT_POLICY_TYPE, CLFS_MGMT_POLICY_TYPE enumeration [Kernel-Mode Driver Architecture], ClfsMgmtPolicyAutoGrow, ClfsMgmtPolicyAutoShrink, ClfsMgmtPolicyGrowthRate, ClfsMgmtPolicyInvalid, ClfsMgmtPolicyLogTail, ClfsMgmtPolicyMaximumSize, ClfsMgmtPolicyMinimumSize, ClfsMgmtPolicyNewContainerExtension, ClfsMgmtPolicyNewContainerPrefix, ClfsMgmtPolicyNewContainerSize, ClfsMgmtPolicyNewContainerSuffix, PCLFS_MGMT_POLICY_TYPE, PCLFS_MGMT_POLICY_TYPE enumeration pointer [Kernel-Mode Driver Architecture], _CLFS_MGMT_POLICY_TYPE, kernel.clfs_mgmt_policy_type, sysenum_bae8275b-5f70-40fb-ae14-f803eaeb0a42.xml, wdm/CLFS_MGMT_POLICY_TYPE, wdm/ClfsMgmtPolicyAutoGrow, wdm/ClfsMgmtPolicyAutoShrink, wdm/ClfsMgmtPolicyGrowthRate, wdm/ClfsMgmtPolicyInvalid, wdm/ClfsMgmtPolicyLogTail, wdm/ClfsMgmtPolicyMaximumSize, wdm/ClfsMgmtPolicyMinimumSize, wdm/ClfsMgmtPolicyNewContainerExtension, wdm/ClfsMgmtPolicyNewContainerPrefix, wdm/ClfsMgmtPolicyNewContainerSize, wdm/ClfsMgmtPolicyNewContainerSuffix, wdm/PCLFS_MGMT_POLICY_TYPE"
f1_keywords:
 - "wdm/CLFS_MGMT_POLICY_TYPE"
req.header: wdm.h
req.include-header: Wdm.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Wdm.h
api_name:
- CLFS_MGMT_POLICY_TYPE
product:
- Windows
targetos: Windows
req.typenames: CLFS_MGMT_POLICY_TYPE, *PCLFS_MGMT_POLICY_TYPE
---

# _CLFS_MGMT_POLICY_TYPE enumeration


## -description


The <b>CLFS_MGMT_POLICY_TYPE</b> enumeration type identifies the type of a CLFS management policy.


## -enum-fields




### -field ClfsMgmtPolicyMaximumSize

Indicates a policy that specifies the maximum size of a log. 


### -field ClfsMgmtPolicyMinimumSize

Indicates a policy that specifies the minimum size of a log. 


### -field ClfsMgmtPolicyNewContainerSize

Indicates a policy that specifies the size of new containers that are created.


### -field ClfsMgmtPolicyGrowthRate

Indicates a policy that specifies how many new containers will be added to the log each time the log grows.


### -field ClfsMgmtPolicyLogTail

Indicates a policy that specifies how much free space will be requested when a client is notified to move its log tail. 


### -field ClfsMgmtPolicyAutoShrink

Indicates a policy that specifies when the log will shrink based on the percentage of the log that is free.


### -field ClfsMgmtPolicyAutoGrow

Indicates a policy that specifies whether the log should grow when fewer than two containers are free.


### -field ClfsMgmtPolicyNewContainerPrefix

Indicates a policy that specifies a prefix for the file name of each container, as well as the full path to the directory where the containers will be placed.


### -field ClfsMgmtPolicyNewContainerSuffix

Indicates a policy that specifies a number to use as the starting suffix for container file names.


### -field ClfsMgmtPolicyNewContainerExtension

Indicates a policy that specifies an extension for the file name of each container.


### -field ClfsMgmtPolicyInvalid

Reserved for internal use.


## -remarks



Each type of CLFS management policy corresponds to a specific interpretation of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_clfs_mgmt_policy">CLFS_MGMT_POLICY</a> structure. The <b>PolicyType</b> member of the <b>CLFS_MGMT_POLICY</b> structure is a valid value of the <b>CLFS_MGMT_POLICY_TYPE</b> enumeration.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_clfs_mgmt_policy">CLFS_MGMT_POLICY</a>
 

 


---
UID: NE:wdm._CLFS_MGMT_POLICY_TYPE
title: "_CLFS_MGMT_POLICY_TYPE"
author: windows-driver-content
description: The CLFS_MGMT_POLICY_TYPE enumeration type identifies the type of a CLFS management policy.
old-location: kernel\clfs_mgmt_policy_type.htm
old-project: kernel
ms.assetid: 50e31ff1-07f2-4781-81f2-8db6e3cf9cc6
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ClfsMgmtPolicyGrowthRate, CLFS_MGMT_POLICY_TYPE enumeration [Kernel-Mode Driver Architecture], wdm/ClfsMgmtPolicyNewContainerExtension, ClfsMgmtPolicyMaximumSize, wdm/ClfsMgmtPolicyLogTail, wdm/ClfsMgmtPolicyMinimumSize, _CLFS_MGMT_POLICY_TYPE, wdm/ClfsMgmtPolicyNewContainerSuffix, wdm/ClfsMgmtPolicyNewContainerSize, wdm/ClfsMgmtPolicyGrowthRate, wdm/ClfsMgmtPolicyInvalid, wdm/ClfsMgmtPolicyAutoGrow, ClfsMgmtPolicyNewContainerSize, PCLFS_MGMT_POLICY_TYPE, ClfsMgmtPolicyAutoShrink, ClfsMgmtPolicyLogTail, CLFS_MGMT_POLICY_TYPE, ClfsMgmtPolicyAutoGrow, wdm/ClfsMgmtPolicyNewContainerPrefix, wdm/ClfsMgmtPolicyAutoShrink, kernel.clfs_mgmt_policy_type, ClfsMgmtPolicyNewContainerExtension, ClfsMgmtPolicyNewContainerPrefix, ClfsMgmtPolicyMinimumSize, PCLFS_MGMT_POLICY_TYPE enumeration pointer [Kernel-Mode Driver Architecture], sysenum_bae8275b-5f70-40fb-ae14-f803eaeb0a42.xml, wdm/CLFS_MGMT_POLICY_TYPE, wdm/PCLFS_MGMT_POLICY_TYPE, ClfsMgmtPolicyInvalid, *PCLFS_MGMT_POLICY_TYPE, ClfsMgmtPolicyNewContainerSuffix, wdm/ClfsMgmtPolicyMaximumSize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wdm.h
apiname:
-	CLFS_MGMT_POLICY_TYPE
product: Windows
targetos: Windows
req.typenames: "*PCLFS_MGMT_POLICY_TYPE, CLFS_MGMT_POLICY_TYPE"
req.product: Windows 10 or later.
---

# _CLFS_MGMT_POLICY_TYPE enumeration


## -description


The <b>CLFS_MGMT_POLICY_TYPE</b> enumeration type identifies the type of a CLFS management policy.


## -syntax


````
typedef enum _CLFS_MGMT_POLICY_TYPE { 
  ClfsMgmtPolicyMaximumSize            = 0,
  ClfsMgmtPolicyMinimumSize            = 1,
  ClfsMgmtPolicyNewContainerSize       = 2,
  ClfsMgmtPolicyGrowthRate             = 3,
  ClfsMgmtPolicyLogTail                = 4,
  ClfsMgmtPolicyAutoShrink             = 5,
  ClfsMgmtPolicyAutoGrow               = 6,
  ClfsMgmtPolicyNewContainerPrefix     = 7,
  ClfsMgmtPolicyNewContainerSuffix     = 8,
  ClfsMgmtPolicyNewContainerExtension  = 9,
  ClfsMgmtPolicyInvalid                = 10
} CLFS_MGMT_POLICY_TYPE, *PCLFS_MGMT_POLICY_TYPE;
````


## -enum-fields




#### - ClfsMgmtPolicyMaximumSize

Indicates a policy that specifies the maximum size of a log. 


#### - ClfsMgmtPolicyMinimumSize

Indicates a policy that specifies the minimum size of a log. 


#### - ClfsMgmtPolicyNewContainerSize

Indicates a policy that specifies the size of new containers that are created.


#### - ClfsMgmtPolicyGrowthRate

Indicates a policy that specifies how many new containers will be added to the log each time the log grows.


#### - ClfsMgmtPolicyLogTail

Indicates a policy that specifies how much free space will be requested when a client is notified to move its log tail. 


#### - ClfsMgmtPolicyAutoShrink

Indicates a policy that specifies when the log will shrink based on the percentage of the log that is free.


#### - ClfsMgmtPolicyAutoGrow

Indicates a policy that specifies whether the log should grow when fewer than two containers are free.


#### - ClfsMgmtPolicyNewContainerPrefix

Indicates a policy that specifies a prefix for the file name of each container, as well as the full path to the directory where the containers will be placed.


#### - ClfsMgmtPolicyNewContainerSuffix

Indicates a policy that specifies a number to use as the starting suffix for container file names.


#### - ClfsMgmtPolicyNewContainerExtension

Indicates a policy that specifies an extension for the file name of each container.


#### - ClfsMgmtPolicyInvalid

Reserved for internal use.


## -remarks


Each type of CLFS management policy corresponds to a specific interpretation of the <a href="..\wdm\ns-wdm-_clfs_mgmt_policy.md">CLFS_MGMT_POLICY</a> structure. The <b>PolicyType</b> member of the <b>CLFS_MGMT_POLICY</b> structure is a valid value of the <b>CLFS_MGMT_POLICY_TYPE</b> enumeration.



## -see-also

<a href="..\wdm\ns-wdm-_clfs_mgmt_policy.md">CLFS_MGMT_POLICY</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20CLFS_MGMT_POLICY_TYPE enumeration%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


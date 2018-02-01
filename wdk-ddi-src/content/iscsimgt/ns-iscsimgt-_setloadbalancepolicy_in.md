---
UID: NS:iscsimgt._SetLoadBalancePolicy_IN
title: "_SetLoadBalancePolicy_IN"
author: windows-driver-content
description: The SetLoadBalancePolicy_IN structure holds the input data for the SetLoadBalance method.
old-location: storage\setloadbalancepolicy_in.htm
old-project: storage
ms.assetid: e1895fed-a006-45f6-a38a-1767202cbf4f
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: PSetLoadBalancePolicy_IN, iscsimgt/SetLoadBalancePolicy_IN, _SetLoadBalancePolicy_IN, PSetLoadBalancePolicy_IN structure pointer [Storage Devices], *PSetLoadBalancePolicy_IN, SetLoadBalancePolicy_IN structure [Storage Devices], structs-iSCSI_d4d805d0-4c3c-4f5e-90ee-9c6bf881dfcf.xml, SetLoadBalancePolicy_IN, iscsimgt/PSetLoadBalancePolicy_IN, storage.setloadbalancepolicy_in
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iscsimgt.h
req.include-header: Iscsimgt.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	iscsimgt.h
apiname:
-	SetLoadBalancePolicy_IN
product: Windows
targetos: Windows
req.typenames: "*PSetLoadBalancePolicy_IN, SetLoadBalancePolicy_IN"
---

# _SetLoadBalancePolicy_IN structure


## -description


The SetLoadBalancePolicy_IN structure holds the input data for the SetLoadBalance method.


## -syntax


````
typedef struct _SetLoadBalancePolicy_IN {
  ISCSI_Supported_LB_Policies LoadBalancePolicies;
} SetLoadBalancePolicy_IN, *PSetLoadBalancePolicy_IN;
````


## -struct-fields




### -field LoadBalancePolicies

A structure that contains the information that is required for setting the load balance policy.


## -remarks


You must implement this class.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff563062">MSiSCSI_LB_Operations WMI Class</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SetLoadBalancePolicy_IN structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


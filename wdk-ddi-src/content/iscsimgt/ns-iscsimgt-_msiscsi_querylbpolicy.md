---
UID: NS:iscsimgt._MSiSCSI_QueryLBPolicy
title: "_MSiSCSI_QueryLBPolicy"
author: windows-driver-content
description: This MSiSCSI_QueryLBPolicy method returns the MCS load balancing policy for each information if any that has been set across different iSCSI session.
old-location: storage\msiscsi_querylbpolicy.htm
old-project: storage
ms.assetid: da45810a-12f2-4242-8428-a1717ecf8af3
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PMSiSCSI_QueryLBPolicy, MSiSCSI_QueryLBPolicy, MSiSCSI_QueryLBPolicy structure [Storage Devices], PMSiSCSI_QueryLBPolicy, PMSiSCSI_QueryLBPolicy structure pointer [Storage Devices], _MSiSCSI_QueryLBPolicy, iscsimgt/MSiSCSI_QueryLBPolicy, iscsimgt/PMSiSCSI_QueryLBPolicy, storage.msiscsi_querylbpolicy, structs-iSCSI_d978106a-8fb4-4b42-8277-8ac767c54d06.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	iscsimgt.h
api_name:
-	MSiSCSI_QueryLBPolicy
product: Windows
targetos: Windows
req.typenames: MSiSCSI_QueryLBPolicy, *PMSiSCSI_QueryLBPolicy
---

# _MSiSCSI_QueryLBPolicy structure


## -description


This MSiSCSI_QueryLBPolicy method returns the MCS load balancing policy for each information if any that has been set across different iSCSI session.


## -syntax


````
typedef struct _MSiSCSI_QueryLBPolicy {
  ULONGLONG                   UniqueAdapterId;
  ULONG                       Reserved;
  ULONG                       SessionCount;
  ISCSI_Supported_LB_Policies LoadBalancePolicies[1];
} MSiSCSI_QueryLBPolicy, *PMSiSCSI_QueryLBPolicy;
````


## -struct-fields




### -field UniqueAdapterId

This is a unique connection identifier that the initiator uses to identify a connection. The <a href="https://msdn.microsoft.com/library/windows/hardware/ff561599">LoginToTarget</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff550121">AddConnectionToSession</a> methods both return this value in the UniqueConnectionId parameter.


### -field Reserved

Reserved for Microsoft use only.


### -field SessionCount

This specifies the number of active sessions for this adapater ID.


### -field LoadBalancePolicies

This is an enumeration that contains information required to set the load balance policy. For more information about how to set the load balance policy, see <a href="..\iscsimgt\ns-iscsimgt-_iscsi_supported_lb_policies.md">ISCSI_Supported_LB_Policies</a>. There will be as many of these structures as the number of sessions available for this adapter.


## -remarks



You must implement this class only if the adapter supports MCS. Otherwise, it is optional.




## -see-also

<a href="..\iscsimgt\ns-iscsimgt-_iscsi_supported_lb_policies.md">ISCSI_Supported_LB_Policies</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550121">AddConnectionToSession</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561599">LoginToTarget</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20MSiSCSI_QueryLBPolicy structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


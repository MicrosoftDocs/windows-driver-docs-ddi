---
UID: NS:iscsimgt._MSiSCSI_QueryLBPolicy
title: _MSiSCSI_QueryLBPolicy (iscsimgt.h)
description: This MSiSCSI_QueryLBPolicy method returns the MCS load balancing policy for each information if any that has been set across different iSCSI session.
old-location: storage\msiscsi_querylbpolicy.htm
tech.root: storage
ms.assetid: da45810a-12f2-4242-8428-a1717ecf8af3
ms.date: 03/29/2018
keywords: ["MSiSCSI_QueryLBPolicy structure"]
ms.keywords: "*PMSiSCSI_QueryLBPolicy, MSiSCSI_QueryLBPolicy, MSiSCSI_QueryLBPolicy structure [Storage Devices], PMSiSCSI_QueryLBPolicy, PMSiSCSI_QueryLBPolicy structure pointer [Storage Devices], _MSiSCSI_QueryLBPolicy, iscsimgt/MSiSCSI_QueryLBPolicy, iscsimgt/PMSiSCSI_QueryLBPolicy, storage.msiscsi_querylbpolicy, structs-iSCSI_d978106a-8fb4-4b42-8277-8ac767c54d06.xml"
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
targetos: Windows
req.typenames: MSiSCSI_QueryLBPolicy, *PMSiSCSI_QueryLBPolicy
f1_keywords:
 - _MSiSCSI_QueryLBPolicy
 - iscsimgt/_MSiSCSI_QueryLBPolicy
 - PMSiSCSI_QueryLBPolicy
 - iscsimgt/PMSiSCSI_QueryLBPolicy
 - MSiSCSI_QueryLBPolicy
 - iscsimgt/MSiSCSI_QueryLBPolicy
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iscsimgt.h
api_name:
 - MSiSCSI_QueryLBPolicy
---

# _MSiSCSI_QueryLBPolicy structure


## -description

This MSiSCSI_QueryLBPolicy method returns the MCS load balancing policy for each information if any that has been set across different iSCSI session.

## -struct-fields

### -field UniqueAdapterId

This is a unique connection identifier that the initiator uses to identify a connection. The <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/logintotarget">LoginToTarget</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/addconnectiontosession">AddConnectionToSession</a> methods both return this value in the UniqueConnectionId parameter.

### -field Reserved

Reserved for Microsoft use only.

### -field SessionCount

This specifies the number of active sessions for this adapater ID.

### -field LoadBalancePolicies

This is an enumeration that contains information required to set the load balance policy. For more information about how to set the load balance policy, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iscsimgt/ns-iscsimgt-_iscsi_supported_lb_policies">ISCSI_Supported_LB_Policies</a>. There will be as many of these structures as the number of sessions available for this adapter.

## -remarks

You must implement this class only if the adapter supports MCS. Otherwise, it is optional.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/addconnectiontosession">AddConnectionToSession</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iscsimgt/ns-iscsimgt-_iscsi_supported_lb_policies">ISCSI_Supported_LB_Policies</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/logintotarget">LoginToTarget</a>


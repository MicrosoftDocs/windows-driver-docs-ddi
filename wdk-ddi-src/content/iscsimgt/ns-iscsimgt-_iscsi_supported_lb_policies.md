---
UID: NS:iscsimgt._ISCSI_Supported_LB_Policies
title: _ISCSI_Supported_LB_Policies (iscsimgt.h)
description: The ISCSI_Supported_LB_Policies structure contains information about load balancing policies for multiple connections per session (MCS).
old-location: storage\iscsi_supported_lb_policies.htm
tech.root: storage
ms.assetid: 053b9f14-7319-4599-886e-3c03c717b348
ms.date: 03/29/2018
ms.keywords: "*PISCSI_Supported_LB_Policies, ISCSI_Supported_LB_Policies, ISCSI_Supported_LB_Policies structure [Storage Devices], PISCSI_Supported_LB_Policies, PISCSI_Supported_LB_Policies structure pointer [Storage Devices], _ISCSI_Supported_LB_Policies, iscsimgt/ISCSI_Supported_LB_Policies, iscsimgt/PISCSI_Supported_LB_Policies, storage.iscsi_supported_lb_policies, structs-iSCSI_4ea7817e-3ec1-46cf-a492-ac327f5d3912.xml"
f1_keywords:
 - "iscsimgt/ISCSI_Supported_LB_Policies"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- iscsimgt.h
api_name:
- ISCSI_Supported_LB_Policies
product:
- Windows
targetos: Windows
req.typenames: ISCSI_Supported_LB_Policies, *PISCSI_Supported_LB_Policies
---

# _ISCSI_Supported_LB_Policies structure


## -description


The ISCSI_Supported_LB_Policies structure contains information about load balancing policies for multiple connections per session (MCS).


## -struct-fields




### -field UniqueSessionId

A 64-bit integer that uniquely identifies the session. The <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/logintotarget">LoginToTarget</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/addconnectiontosession">AddConnectionToSession</a> methods both return this value in their UniqueSessionId parameter. Do not confuse this value with the values in the ISID and TSID members.


### -field LoadBalancePolicy

This specifies the type of load balance policy that has been established on a multiconnection session.

<table>
<tr>
<th>Type</th>
<th>Meaning</th>
</tr>
<tr>
<td>
MSiSCSI_LB_FAILOVER

</td>
<td>
An alternate path  is used only for failover.

</td>
</tr>
<tr>
<td>
MSiSCSI_LB_ROUND_ROBIN

</td>
<td>
I/O operations are scheduled to all active paths in a round-robin fashion.

</td>
</tr>
<tr>
<td>
MSiSCSI_LB_ROUND_ROBIN_WITH_SUBSET

</td>
<td>
I/O operations are scheduled to all paths within a subset in a round-robin fashion.

</td>
</tr>
<tr>
<td>
MSiSCSI_LB_DYN_LEAST_QUEUE_DEPTH

</td>
<td>
I/O operations are balanced across a set of paths based on the least queue depth mechanism (I/O is scheduled to the path with the fewest pending I/Os in its queue).

</td>
</tr>
<tr>
<td>
MSiSCSI_LB_WEIGHTED_PATHS

</td>
<td>
I/O operations are scheduled based on the weights assigned to a path by an administrator.

</td>
</tr>
<tr>
<td>
MSiSCSI_LB_VENDOR_SPECIFIC

</td>
<td>
Vendor-specific I/O policies are in effect.

</td>
</tr>
</table>
 


### -field iSCSI_PathCount

The number of paths associated with a target in the context of this session.


### -field iSCSI_Paths

Path information as shown in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iscsimgt/ns-iscsimgt-_iscsi_path">ISCSI_Path</a> structure.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/addconnectiontosession">AddConnectionToSession</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/logintotarget">LoginToTarget</a>
 

 


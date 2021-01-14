---
UID: NS:iscsimgt._MSiSCSI_InitiatorNodeFailureEvent
title: _MSiSCSI_InitiatorNodeFailureEvent (iscsimgt.h)
description: The MSiSCSI_InitiatorNodeFailureEvent structure is used to report an event when a node failure occurs.
old-location: storage\msiscsi_initiatornodefailureevent.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["MSiSCSI_InitiatorNodeFailureEvent structure"]
ms.keywords: "*PMSiSCSI_InitiatorNodeFailureEvent, MSiSCSI_InitiatorNodeFailureEvent, MSiSCSI_InitiatorNodeFailureEvent structure [Storage Devices], PMSiSCSI_InitiatorNodeFailureEvent, PMSiSCSI_InitiatorNodeFailureEvent structure pointer [Storage Devices], _MSiSCSI_InitiatorNodeFailureEvent, iscsimgt/MSiSCSI_InitiatorNodeFailureEvent, iscsimgt/PMSiSCSI_InitiatorNodeFailureEvent, storage.msiscsi_initiatornodefailureevent, structs-iSCSI_0d1bb4bf-74a0-4d99-9bf8-1545faaff14d.xml"
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
req.typenames: MSiSCSI_InitiatorNodeFailureEvent, *PMSiSCSI_InitiatorNodeFailureEvent
f1_keywords:
 - _MSiSCSI_InitiatorNodeFailureEvent
 - iscsimgt/_MSiSCSI_InitiatorNodeFailureEvent
 - PMSiSCSI_InitiatorNodeFailureEvent
 - iscsimgt/PMSiSCSI_InitiatorNodeFailureEvent
 - MSiSCSI_InitiatorNodeFailureEvent
 - iscsimgt/MSiSCSI_InitiatorNodeFailureEvent
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iscsimgt.h
api_name:
 - _MSiSCSI_InitiatorNodeFailureEvent
 - PMSiSCSI_InitiatorNodeFailureEvent
 - MSiSCSI_InitiatorNodeFailureEvent
---

# _MSiSCSI_InitiatorNodeFailureEvent structure


## -description

The MSiSCSI_InitiatorNodeFailureEvent structure is used to report an event when a node failure occurs.

## -struct-fields

### -field FailureTime

A timestamp that indicates when the node failure occurred.

### -field FailureType

The type of node failure. This member can have the following integer values, which are defined in a ValueMap in <i>Mgmt.mof</i>.

<table>
<tr>
<th>Value</th>
<th>Failure type</th>
</tr>
<tr>
<td>
LoginOtherFail

</td>
<td>
The logon failed for unspecified reasons. 

</td>
</tr>
<tr>
<td>
LoginAuthFail

</td>
<td>
The logon failed, because the initiator and target do not have compatible authentication algorithms. 

</td>
</tr>
<tr>
<td>
LoginAuthenticateFail

</td>
<td>
The logon failed, because the credentials of the initiator and target do not match and the initiator could not authenticate the target. 

</td>
</tr>
<tr>
<td>
LoginNegotiateFail

</td>
<td>
The logon failed, because the initiator could not successfully negotiate a connection with the target. 

</td>
</tr>
<tr>
<td>
LogoutOthers

</td>
<td>
The logout failed due to other reasons.

</td>
</tr>
</table>

### -field TargetFailureName

A wide character string that specifies the name of the target that a logon or logoff failed for.

### -field TargetFailureAddr

A <a href="/windows-hardware/drivers/ddi/iscsidef/ns-iscsidef-_iscsi_ip_address">ISCSI_IP_Address</a> structure that specifies the IP address of the target that a logon or logoff failed for.

## -remarks

It is optional that you implement this class.

## -see-also

<a href="/windows-hardware/drivers/ddi/iscsidef/ns-iscsidef-_iscsi_ip_address">ISCSI_IP_Address</a>



<a href="/windows-hardware/drivers/storage/msiscsi-initiatornodefailureevent-wmi-class">MSiSCSI_InitiatorNodeFailureEvent WMI Class</a>


---
UID: NS:iscsimgt._MSiSCSI_InitiatorNodeFailureEvent
title: "_MSiSCSI_InitiatorNodeFailureEvent"
author: windows-driver-content
description: The MSiSCSI_InitiatorNodeFailureEvent structure is used to report an event when a node failure occurs.
old-location: storage\msiscsi_initiatornodefailureevent.htm
old-project: storage
ms.assetid: 0d761b64-d405-4c19-9fd8-e4bf371515a1
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PMSiSCSI_InitiatorNodeFailureEvent, MSiSCSI_InitiatorNodeFailureEvent, MSiSCSI_InitiatorNodeFailureEvent structure [Storage Devices], PMSiSCSI_InitiatorNodeFailureEvent, PMSiSCSI_InitiatorNodeFailureEvent structure pointer [Storage Devices], _MSiSCSI_InitiatorNodeFailureEvent, iscsimgt/MSiSCSI_InitiatorNodeFailureEvent, iscsimgt/PMSiSCSI_InitiatorNodeFailureEvent, storage.msiscsi_initiatornodefailureevent, structs-iSCSI_0d1bb4bf-74a0-4d99-9bf8-1545faaff14d.xml"
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
-	MSiSCSI_InitiatorNodeFailureEvent
product: Windows
targetos: Windows
req.typenames: MSiSCSI_InitiatorNodeFailureEvent, *PMSiSCSI_InitiatorNodeFailureEvent
---

# _MSiSCSI_InitiatorNodeFailureEvent structure


## -description


The MSiSCSI_InitiatorNodeFailureEvent structure is used to report an event when a node failure occurs.


## -syntax


````
typedef struct _MSiSCSI_InitiatorNodeFailureEvent {
  ULONGLONG        FailureTime;
  UCHAR            FailureType;
  WCHAR            TargetFailureName[223 + 1];
  ISCSI_IP_Address TargetFailureAddr;
} MSiSCSI_InitiatorNodeFailureEvent, *PMSiSCSI_InitiatorNodeFailureEvent;
````


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

A <a href="..\iscsidef\ns-iscsidef-_iscsi_ip_address.md">ISCSI_IP_Address</a> structure that specifies the IP address of the target that a logon or logoff failed for.


## -remarks



It is optional that you implement this class.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff563049">MSiSCSI_InitiatorNodeFailureEvent WMI Class</a>



<a href="..\iscsidef\ns-iscsidef-_iscsi_ip_address.md">ISCSI_IP_Address</a>



 

 



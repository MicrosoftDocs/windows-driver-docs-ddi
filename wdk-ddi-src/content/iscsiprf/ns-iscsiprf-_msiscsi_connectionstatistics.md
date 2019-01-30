---
UID: NS:iscsiprf._MSiSCSI_ConnectionStatistics
title: _MSiSCSI_ConnectionStatistics (iscsiprf.h)
description: The MSiSCSI_ConnectionStatistics structure is used by iSCSI initiators to report statistics for a connection within a session.
old-location: storage\msiscsi_connectionstatistics.htm
tech.root: storage
ms.assetid: f1f38292-604f-4618-b6ec-f3822d60a96c
ms.date: 03/29/2018
ms.keywords: "*PMSiSCSI_ConnectionStatistics, MSiSCSI_ConnectionStatistics, MSiSCSI_ConnectionStatistics structure [Storage Devices], PMSiSCSI_ConnectionStatistics, PMSiSCSI_ConnectionStatistics structure pointer [Storage Devices], _MSiSCSI_ConnectionStatistics, iscsiprf/MSiSCSI_ConnectionStatistics, iscsiprf/PMSiSCSI_ConnectionStatistics, storage.msiscsi_connectionstatistics, structs-iSCSI_6a149338-4636-45cd-9c15-2444e2ebcd1a.xml"
ms.topic: struct
req.header: iscsiprf.h
req.include-header: Iscsiprf.h
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
-	iscsiprf.h
api_name:
-	MSiSCSI_ConnectionStatistics
product:
- Windows
targetos: Windows
req.typenames: MSiSCSI_ConnectionStatistics, *PMSiSCSI_ConnectionStatistics
---

# _MSiSCSI_ConnectionStatistics structure


## -description


The <b>MSiSCSI_ConnectionStatistics</b> structure is used by iSCSI initiators to report statistics for a connection within a session. 


## -struct-fields




### -field iSCSIName

A wide character string that contains the name of the iSCSI target.


### -field CID

The iSCSI connection identifier (ID) for this connection instance. This ID is an internal value that the iSCSI protocol uses to identify the connection. Do not use this ID. Application software should use the connection identifier that the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561599">LoginToTarget</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff550121">AddConnectionToSession</a> methods return in the <i>UniqueConnectionId</i> parameter.


### -field USID

The iSCSI session ID for this connection instance. This ID is an internal value that the iSCSI protocol uses to identify the session. Application software should use the session identifier that the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561599">LoginToTarget</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff550121">AddConnectionToSession</a> methods return in the <i>UniqueSessionId</i> parameter.


### -field UniqueAdapterId

A 64-bit integer that uniquely identifies an HBA initiator and a loaded instance of a storage miniport driver that manages the HBA. The initiator should use the address of the adapter extension or another address that the device driver owns to construct this ID. The initiator reports this value in the <b>UniqueAdapterId</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563012">MSiSCSI_HBAInformation</a> structure.


### -field BytesSent

The number of bytes that are sent over this connection. 


### -field BytesReceived

The number of bytes that are received over this connection. 


### -field PDUCommandsSent

The number of PDUs that are sent over this connection. 


### -field PDUResponsesReceived

The number of PDUs that are received over this connection.


## -remarks



Initiators must register the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562989">MSiSCSI_ConnectionStatistics WMI Class</a> with the following dynamic instance name for the connection: 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>targetname_#:#</pre>
</td>
</tr>
</table></span></div>
The first number sign (#) is the value in the <b>USID</b> member of <b>MSiSCSI_ConnectionStatistics</b>, and the second number sign (#) is the value in the <b>CID</b> member. It is optional that you implement this class.

The totals tracked by this structure are valid for the lifetime of the connection in the session. Totals for all connections in a session are obtained in <a href="https://msdn.microsoft.com/library/windows/hardware/ff563137">MSiSCSI_SessionStatistics</a> structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550121">AddConnectionToSession</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561599">LoginToTarget</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562989">MSiSCSI_ConnectionStatistics WMI Class</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563012">MSiSCSI_HBAInformation</a>
 

 


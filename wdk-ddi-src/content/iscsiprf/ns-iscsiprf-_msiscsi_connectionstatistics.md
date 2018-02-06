---
UID: NS:iscsiprf._MSiSCSI_ConnectionStatistics
title: "_MSiSCSI_ConnectionStatistics"
author: windows-driver-content
description: The MSiSCSI_ConnectionStatistics structure is used by iSCSI initiators to report statistics for a connection within a session.
old-location: storage\msiscsi_connectionstatistics.htm
old-project: storage
ms.assetid: f1f38292-604f-4618-b6ec-f3822d60a96c
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: PMSiSCSI_ConnectionStatistics, iscsiprf/MSiSCSI_ConnectionStatistics, *PMSiSCSI_ConnectionStatistics, MSiSCSI_ConnectionStatistics structure [Storage Devices], iscsiprf/PMSiSCSI_ConnectionStatistics, storage.msiscsi_connectionstatistics, _MSiSCSI_ConnectionStatistics, MSiSCSI_ConnectionStatistics, PMSiSCSI_ConnectionStatistics structure pointer [Storage Devices], structs-iSCSI_6a149338-4636-45cd-9c15-2444e2ebcd1a.xml
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	iscsiprf.h
apiname:
-	MSiSCSI_ConnectionStatistics
product: Windows
targetos: Windows
req.typenames: "*PMSiSCSI_ConnectionStatistics, MSiSCSI_ConnectionStatistics"
---

# _MSiSCSI_ConnectionStatistics structure


## -description


The <b>MSiSCSI_ConnectionStatistics</b> structure is used by iSCSI initiators to report statistics for a connection within a session. 


## -syntax


````
typedef struct _MSiSCSI_ConnectionStatistics {
  WCHAR     iSCSIName[223 + 1];
  USHORT    CID;
  ULONGLONG USID;
  ULONGLONG UniqueAdapterId;
  ULONGLONG BytesSent;
  ULONGLONG BytesReceived;
  ULONGLONG PDUCommandsSent;
  ULONGLONG PDUResponsesReceived;
} MSiSCSI_ConnectionStatistics, *PMSiSCSI_ConnectionStatistics;
````


## -struct-fields




### -field iSCSIName

A wide character string that contains the name of the iSCSI target.


### -field CID

The iSCSI connection identifier (ID) for this connection instance. This ID is an internal value that the iSCSI protocol uses to identify the connection. Do not use this ID. Application software should use the connection identifier that the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561599">LoginToTarget</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff550121">AddConnectionToSession</a> methods return in the <i>UniqueConnectionId</i> parameter.


### -field USID

The iSCSI session ID for this connection instance. This ID is an internal value that the iSCSI protocol uses to identify the session. Application software should use the session identifier that the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561599">LoginToTarget</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff550121">AddConnectionToSession</a> methods return in the <i>UniqueSessionId</i> parameter.


### -field UniqueAdapterId

A 64-bit integer that uniquely identifies an HBA initiator and a loaded instance of a storage miniport driver that manages the HBA. The initiator should use the address of the adapter extension or another address that the device driver owns to construct this ID. The initiator reports this value in the <b>UniqueAdapterId</b> member of the <a href="..\iscsimgt\ns-iscsimgt-_msiscsi_hbainformation.md">MSiSCSI_HBAInformation</a> structure.


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
</table></span></div>The first number sign (#) is the value in the <b>USID</b> member of <b>MSiSCSI_ConnectionStatistics</b>, and the second number sign (#) is the value in the <b>CID</b> member. It is optional that you implement this class.

The totals tracked by this structure are valid for the lifetime of the connection in the session. Totals for all connections in a session are obtained in <a href="..\iscsiprf\ns-iscsiprf-_msiscsi_sessionstatistics.md">MSiSCSI_SessionStatistics</a> structure.



## -see-also

<a href="..\iscsimgt\ns-iscsimgt-_msiscsi_hbainformation.md">MSiSCSI_HBAInformation</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550121">AddConnectionToSession</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff562989">MSiSCSI_ConnectionStatistics WMI Class</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561599">LoginToTarget</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20MSiSCSI_ConnectionStatistics structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


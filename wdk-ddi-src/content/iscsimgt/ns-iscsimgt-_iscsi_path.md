---
UID: NS:iscsimgt._ISCSI_Path
title: "_ISCSI_Path"
author: windows-driver-content
description: The ISCSI_Path structure contains information about a connection of the iSCSI portal.
old-location: storage\iscsi_path.htm
old-project: storage
ms.assetid: eebc3e2e-41fe-4087-8916-7c8a71929913
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PISCSI_Path, ISCSI_Path, ISCSI_Path structure [Storage Devices], PISCSI_Path, PISCSI_Path structure pointer [Storage Devices], _ISCSI_Path, iscsimgt/ISCSI_Path, iscsimgt/PISCSI_Path, storage.iscsi_path, structs-iSCSI_fe9f6ee9-2fcd-46eb-a010-98e82dbf8c70.xml"
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
-	ISCSI_Path
product: Windows
targetos: Windows
req.typenames: ISCSI_Path, *PISCSI_Path
---

# _ISCSI_Path structure


## -description


The ISCSI_Path structure contains information about a connection of the iSCSI portal.


## -syntax


````
typedef struct _ISCSI_Path {
  ULONGLONG UniqueConnectionId;
  ULONGLONG EstimatedLinkSpeed;
  ULONG     PathWeight;
  ULONG     PrimaryPath;
  ULONG     ConnectionStatus;
  ULONG     TCPOffLoadAvailable;
} ISCSI_Path, *PISCSI_Path;
````


## -struct-fields




### -field UniqueConnectionId

This is a unique connection identifier that the initiator uses to identify a connection. The <a href="https://msdn.microsoft.com/library/windows/hardware/ff561599">LoginToTarget</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff550121">AddConnectionToSession</a> methods both return this value in the UniqueConnectionId parameter.  This value is not to be confused with the connection ID (CID).


### -field EstimatedLinkSpeed

This specifies the connection speed in megabits per second (Mbps).


### -field PathWeight

This specifies the weight assigned to this path. The value can be any 32-bit number, with a higher number that signifies a higher priority. If more than one path is available, this path weight value is compared against each other path weight and will be prioritized accordingly. For example, if a value of 1 is used for path1 and a value of 2 for path2, path2 has higher priority.


### -field PrimaryPath

This specifies the state of the path: primary or secondary. If the value is 1, it means the path is the primary path, and if it is 0, it is a secondary path.


### -field ConnectionStatus

This indicates the status of the connection.

<table>
<tr>
<th>Type</th>
<th>Meaning</th>
</tr>
<tr>
<td>
CONNECTION_STATE_CONNECTED (1)

</td>
<td>
The path is connected and active.

</td>
</tr>
<tr>
<td>
CONNECTION_STATE_DISCONNECTED (2)

</td>
<td>
The path is disconnected.

</td>
</tr>
<tr>
<td>
CONNECTION_STATE_RECONNECTING(3)

</td>
<td>
The path is reconnecting.

</td>
</tr>
</table>
 


### -field TCPOffLoadAvailable

This indicates whether the connection supports TCP offload or not.


## -remarks



The iSCSI headers and MOF are included in the platform SDK and WDK.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561599">LoginToTarget</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550121">AddConnectionToSession</a>



 

 



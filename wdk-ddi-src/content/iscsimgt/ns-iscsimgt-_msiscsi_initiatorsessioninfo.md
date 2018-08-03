---
UID: NS:iscsimgt._MSiSCSI_InitiatorSessionInfo
title: "_MSiSCSI_InitiatorSessionInfo"
author: windows-driver-content
description: The MSiSCSI_InitiatorSessionInfo structure contains information about a collection of sessions that belong to the indicated HBA initiator.
old-location: storage\msiscsi_initiatorsessioninfo.htm
tech.root: storage
ms.assetid: 0406efa5-26ad-4a3d-829b-d9b03b7c3b26
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PMSiSCSI_InitiatorSessionInfo, MSiSCSI_InitiatorSessionInfo, MSiSCSI_InitiatorSessionInfo structure [Storage Devices], PMSiSCSI_InitiatorSessionInfo, PMSiSCSI_InitiatorSessionInfo structure pointer [Storage Devices], _MSiSCSI_InitiatorSessionInfo, iscsimgt/MSiSCSI_InitiatorSessionInfo, iscsimgt/PMSiSCSI_InitiatorSessionInfo, storage.msiscsi_initiatorsessioninfo, structs-iSCSI_a3ebb8e8-47ff-4482-b896-7b310216bdf1.xml"
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
-	MSiSCSI_InitiatorSessionInfo
product:
- Windows
targetos: Windows
req.typenames: MSiSCSI_InitiatorSessionInfo, *PMSiSCSI_InitiatorSessionInfo
---

# _MSiSCSI_InitiatorSessionInfo structure


## -description


The MSiSCSI_InitiatorSessionInfo structure contains information about a collection of sessions that belong to the indicated HBA initiator.


## -struct-fields




### -field UniqueAdapterId

A 64-bit integer that uniquely identifies an HBA initiator and a loaded instance of a storage miniport driver that manages the HBA. The initiator should use the address of the adapter extension or another address that the device driver owns to construct this identifier (ID). The initiator reports this value in the <b>UniqueAdapterId</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563012">MSiSCSI_HBAInformation</a> structure.


### -field SessionCount

The number of sessions that have been established with the provided adapter ID.


### -field SessionsList

A variable length array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff561565">ISCSI_SessionStaticInfo</a> structures, which describe the static information that is associated with a session.


## -remarks



You must implement this class.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561565">ISCSI_SessionStaticInfo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563012">MSiSCSI_HBAInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563057">MSiSCSI_InitiatorSessionInfo WMI Class</a>
 

 


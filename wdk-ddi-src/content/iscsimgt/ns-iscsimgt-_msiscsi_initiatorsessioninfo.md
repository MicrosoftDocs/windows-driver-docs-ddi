---
UID: NS:iscsimgt._MSiSCSI_InitiatorSessionInfo
title: "_MSiSCSI_InitiatorSessionInfo"
author: windows-driver-content
description: The MSiSCSI_InitiatorSessionInfo structure contains information about a collection of sessions that belong to the indicated HBA initiator.
old-location: storage\msiscsi_initiatorsessioninfo.htm
old-project: storage
ms.assetid: 0406efa5-26ad-4a3d-829b-d9b03b7c3b26
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: MSiSCSI_InitiatorSessionInfo, iscsimgt/PMSiSCSI_InitiatorSessionInfo, PMSiSCSI_InitiatorSessionInfo structure pointer [Storage Devices], storage.msiscsi_initiatorsessioninfo, PMSiSCSI_InitiatorSessionInfo, structs-iSCSI_a3ebb8e8-47ff-4482-b896-7b310216bdf1.xml, iscsimgt/MSiSCSI_InitiatorSessionInfo, _MSiSCSI_InitiatorSessionInfo, MSiSCSI_InitiatorSessionInfo structure [Storage Devices], *PMSiSCSI_InitiatorSessionInfo
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
-	MSiSCSI_InitiatorSessionInfo
product: Windows
targetos: Windows
req.typenames: MSiSCSI_InitiatorSessionInfo, *PMSiSCSI_InitiatorSessionInfo
---

# _MSiSCSI_InitiatorSessionInfo structure


## -description


The MSiSCSI_InitiatorSessionInfo structure contains information about a collection of sessions that belong to the indicated HBA initiator.


## -syntax


````
typedef struct _MSiSCSI_InitiatorSessionInfo {
  ULONGLONG               UniqueAdapterId;
  ULONG                   SessionCount;
  ISCSI_SessionStaticInfo SessionsList[1];
} MSiSCSI_InitiatorSessionInfo, *PMSiSCSI_InitiatorSessionInfo;
````


## -struct-fields




### -field UniqueAdapterId

A 64-bit integer that uniquely identifies an HBA initiator and a loaded instance of a storage miniport driver that manages the HBA. The initiator should use the address of the adapter extension or another address that the device driver owns to construct this identifier (ID). The initiator reports this value in the <b>UniqueAdapterId</b> member of the <a href="..\iscsimgt\ns-iscsimgt-_msiscsi_hbainformation.md">MSiSCSI_HBAInformation</a> structure.


### -field SessionCount

The number of sessions that have been established with the provided adapter ID.


### -field SessionsList

A variable length array of <a href="..\iscsimgt\ns-iscsimgt-_iscsi_sessionstaticinfo.md">ISCSI_SessionStaticInfo</a> structures, which describe the static information that is associated with a session.


## -remarks


You must implement this class.



## -see-also

<a href="..\iscsimgt\ns-iscsimgt-_iscsi_sessionstaticinfo.md">ISCSI_SessionStaticInfo</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff563057">MSiSCSI_InitiatorSessionInfo WMI Class</a>

<a href="..\iscsimgt\ns-iscsimgt-_msiscsi_hbainformation.md">MSiSCSI_HBAInformation</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20MSiSCSI_InitiatorSessionInfo structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


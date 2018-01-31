---
UID: NS:iscsimgt._MSiSCSI_InitiatorInstanceFailureEvent
title: "_MSiSCSI_InitiatorInstanceFailureEvent"
author: windows-driver-content
description: The MSiSCSI_InitiatorInstanceFailureEvent structure is used to report an event when an initiator instance failure occurs.
old-location: storage\msiscsi_initiatorinstancefailureevent.htm
old-project: storage
ms.assetid: f0213dc9-7299-4cf7-b2c9-27e5d1caea00
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: iscsimgt/MSiSCSI_InitiatorInstanceFailureEvent, structs-iSCSI_189ce06c-9fb3-49f5-9921-31c400c4ae23.xml, MSiSCSI_InitiatorInstanceFailureEvent structure [Storage Devices], PMSiSCSI_InitiatorInstanceFailureEvent structure pointer [Storage Devices], _MSiSCSI_InitiatorInstanceFailureEvent, iscsimgt/PMSiSCSI_InitiatorInstanceFailureEvent, MSiSCSI_InitiatorInstanceFailureEvent, storage.msiscsi_initiatorinstancefailureevent, *PMSiSCSI_InitiatorInstanceFailureEvent, PMSiSCSI_InitiatorInstanceFailureEvent
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
-	MSiSCSI_InitiatorInstanceFailureEvent
product: Windows
targetos: Windows
req.typenames: "*PMSiSCSI_InitiatorInstanceFailureEvent, MSiSCSI_InitiatorInstanceFailureEvent"
---

# _MSiSCSI_InitiatorInstanceFailureEvent structure


## -description


The MSiSCSI_InitiatorInstanceFailureEvent structure is used to report an event when an initiator instance failure occurs.


## -syntax


````
typedef struct _MSiSCSI_InitiatorInstanceFailureEvent {
  UCHAR FailureType;
  WCHAR RemoteNodeName[223 + 1];
} MSiSCSI_InitiatorInstanceFailureEvent, *PMSiSCSI_InitiatorInstanceFailureEvent;
````


## -struct-fields




#### - FailureType

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff561533">ISCSI_INITIATOR_FAILURE_TYPE_QUALIFIERS</a> value that indicates why the initiator instance failed.


#### - RemoteNodeName

The name of the target that is associated with the initiator instance that is reporting a failure.


## -remarks


We recommend that you implement this class.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561533">ISCSI_INITIATOR_FAILURE_TYPE_QUALIFIERS</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff563032">MSiSCSI_InitiatorInstanceFailureEvent WMI Class</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20MSiSCSI_InitiatorInstanceFailureEvent structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


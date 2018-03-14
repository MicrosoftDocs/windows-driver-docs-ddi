---
UID: NS:iscsimgt._MSiSCSI_InitiatorInstanceFailureEvent
title: "_MSiSCSI_InitiatorInstanceFailureEvent"
author: windows-driver-content
description: The MSiSCSI_InitiatorInstanceFailureEvent structure is used to report an event when an initiator instance failure occurs.
old-location: storage\msiscsi_initiatorinstancefailureevent.htm
old-project: storage
ms.assetid: f0213dc9-7299-4cf7-b2c9-27e5d1caea00
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PMSiSCSI_InitiatorInstanceFailureEvent, MSiSCSI_InitiatorInstanceFailureEvent, MSiSCSI_InitiatorInstanceFailureEvent structure [Storage Devices], PMSiSCSI_InitiatorInstanceFailureEvent, PMSiSCSI_InitiatorInstanceFailureEvent structure pointer [Storage Devices], _MSiSCSI_InitiatorInstanceFailureEvent, iscsimgt/MSiSCSI_InitiatorInstanceFailureEvent, iscsimgt/PMSiSCSI_InitiatorInstanceFailureEvent, storage.msiscsi_initiatorinstancefailureevent, structs-iSCSI_189ce06c-9fb3-49f5-9921-31c400c4ae23.xml"
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
-	MSiSCSI_InitiatorInstanceFailureEvent
product: Windows
targetos: Windows
req.typenames: MSiSCSI_InitiatorInstanceFailureEvent, *PMSiSCSI_InitiatorInstanceFailureEvent
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




### -field FailureType

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff561533">ISCSI_INITIATOR_FAILURE_TYPE_QUALIFIERS</a> value that indicates why the initiator instance failed.


### -field RemoteNodeName

The name of the target that is associated with the initiator instance that is reporting a failure.


## -remarks



We recommend that you implement this class.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561533">ISCSI_INITIATOR_FAILURE_TYPE_QUALIFIERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563032">MSiSCSI_InitiatorInstanceFailureEvent WMI Class</a>



 

 



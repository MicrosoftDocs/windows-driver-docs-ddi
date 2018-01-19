---
UID: NE:iscsiop.PISCSI_ADAPTER_EVENT_CODE
title: *PISCSI_ADAPTER_EVENT_CODE
author: windows-driver-content
description: The ISCSI_ADAPTER_EVENT_CODE enumeration indicates the type of adapter event.
old-location: storage\iscsi_adapter_event_code.htm
old-project: storage
ms.assetid: 65fa2307-8d71-4c83-86b3-a965bd7f3da8
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: *PISCSI_ADAPTER_EVENT_CODE, *PISCSI_ADAPTER_EVENT_CODE, ISCSI_ADAPTER_EVENT_CODE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: iscsiop.h
req.include-header: Iscsiop.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ISCSI_ADAPTER_EVENT_CODE
req.alt-loc: iscsiop.h
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
req.typenames: *PISCSI_ADAPTER_EVENT_CODE, ISCSI_ADAPTER_EVENT_CODE
---

# *PISCSI_ADAPTER_EVENT_CODE enumeration



## -description
The ISCSI_ADAPTER_EVENT_CODE enumeration indicates the type of adapter event.



## -syntax

````
typedef enum  { 
  ISCSI_ADAPTER_TARGETS_CHANGED  = 3
} ISCSI_ADAPTER_EVENT_CODE, *PISCSI_ADAPTER_EVENT_CODE;
````


## -enum-fields

### -field ISCSI_ADAPTER_TARGETS_CHANGED

An adapter discovered that its list of targets changed. 


## -remarks


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff562971">MSiSCSI_AdapterEvent WMI Class</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ISCSI_ADAPTER_EVENT_CODE enumeration%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


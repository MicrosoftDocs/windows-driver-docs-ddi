---
UID: NS:61883._CMP_NOTIFY_INFO
title: _CMP_NOTIFY_INFO
author: windows-driver-content
description: This structure is used by the PCMP_NOTIFY_ROUTINE callback.
old-location: ieee\cmp_notify_info.htm
old-project: IEEE
ms.assetid: 7451B01F-D925-4882-9E6B-EEA79F54C55B
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _CMP_NOTIFY_INFO, *PCMP_NOTIFY_INFO, CMP_NOTIFY_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: 61883.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CMP_NOTIFY_INFO
req.alt-loc: 61883.h
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
req.typenames: *PCMP_NOTIFY_INFO, CMP_NOTIFY_INFO
---

# _CMP_NOTIFY_INFO structure



## -description
This structure is used by the <a href="..\61883\nc-61883-pcmp_notify_routine.md">PCMP_NOTIFY_ROUTINE</a> callback.



## -syntax

````
typedef struct _CMP_NOTIFY_INFO {
  HANDLE hPlug;
  AV_PCR Pcr;
  PVOID  Context;
} CMP_NOTIFY_INFO, *PCMP_NOTIFY_INFO;
````


## -struct-fields

### -field hPlug

The handle of a plug for the notification.


### -field Pcr

A plug control register.


### -field Context

A context.


## -remarks


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537008">AV_61883_REQUEST</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [IEEE\buses]:%20CMP_NOTIFY_INFO structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


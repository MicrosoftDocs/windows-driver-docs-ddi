---
UID: NF:wdm.EtwEventEnabled
title: EtwEventEnabled function
author: windows-driver-content
description: The EtwEventEnabled function verifies whether an event is enabled.
old-location: devtest\etweventenabled.htm
old-project: devtest
ms.assetid: 19aa5905-f611-46e2-8d70-a6cc4649c911
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: EtwEventEnabled
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: EtwEventEnabled
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# EtwEventEnabled function



## -description
The <b>EtwEventEnabled</b> function verifies whether an event is enabled.



## -syntax

````
BOOLEAN EtwEventEnabled(
  _In_ REGHANDLE          RegHandle,
  _In_ PCEVENT_DESCRIPTOR EventDescriptor
);
````


## -parameters

### -param RegHandle [in]

A pointer to the event provider registration handle, which is returned by the 
      <b>EtwRegister</b> function if the event provider registration is successful.


### -param EventDescriptor [in]

A pointer to a constant EVENT_DESCRIPTOR. 


## -returns
The <b>EtwEventEnabled</b> function returns <b>TRUE</b> if the 
      event is enabled and <b>FALSE</b> if the event is not enabled.


## -remarks
If logging an event requires additional computing, the <b>EtwEventEnabled</b> 
     function can be used to determine whether the event is going to be logged, which will minimize the overhead when 
     logging is disabled.

If the event descriptor is not available, use the 
     <a href="..\wdm\nf-wdm-etwproviderenabled.md">EtwProviderEnabled</a> function instead.


## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-etwproviderenabled.md">EtwProviderEnabled</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [devtest\devtest]:%20EtwEventEnabled function%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


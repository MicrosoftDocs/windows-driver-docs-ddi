---
UID: NF:wdm.IoGetIoPriorityHint
title: IoGetIoPriorityHint function
author: windows-driver-content
description: The IoGetIoPriorityHint routine gets the priority hint value from an IRP.
old-location: kernel\iogetiopriorityhint.htm
old-project: kernel
ms.assetid: eddb6cea-74fc-4faf-85fa-3a35d6890802
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: IoGetIoPriorityHint
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IoGetIoPriorityHint
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

# IoGetIoPriorityHint function



## -description
The <b>IoGetIoPriorityHint</b> routine gets the <a href="https://msdn.microsoft.com/c34afff2-32f2-451b-ab16-ff048d5c3204">priority hint value</a> from an IRP.



## -syntax

````
IO_PRIORITY_HINT IoGetIoPriorityHint(
  _In_ PIRP Irp
);
````


## -parameters

### -param Irp [in]

Specifies the IRP to obtain the priority hint from.


## -returns
<b>IoGetIoPriorityHint</b> returns the <a href="..\wdm\ne-wdm-_io_priority_hint.md">IO_PRIORITY_HINT</a> value that indicates the current priority hint.


## -remarks
For more information about priority hints, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565403">Using IRP Priority Hints</a>.


## -see-also
<dl>
<dt>
<a href="..\wdm\ne-wdm-_io_priority_hint.md">IO_PRIORITY_HINT</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iosetiopriorityhint.md">IoSetIoPriorityHint</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoGetIoPriorityHint routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


---
UID: NF:ntddk.PsGetCurrentThreadId
title: PsGetCurrentThreadId function
author: windows-driver-content
description: The PsGetCurrentThreadId routine identifies the current thread.
old-location: kernel\psgetcurrentthreadid.htm
old-project: kernel
ms.assetid: c4da1dcb-435d-4e32-8114-3b0ae4352000
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: PsGetCurrentThreadId
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PsGetCurrentThreadId
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
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# PsGetCurrentThreadId function



## -description
The <b>PsGetCurrentThreadId</b> routine identifies the current thread. 



## -syntax

````
HANDLE PsGetCurrentThreadId(void);
````


## -parameters


## -returns
The <b>PsGetCurrentThreadId</b> routine returns the thread ID of the current thread. 

The <b>PsGetCurrentThreadId</b> routine returns the thread ID of the current thread. 

The <b>PsGetCurrentThreadId</b> routine returns the thread ID of the current thread. 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-kegetcurrentthread.md">KeGetCurrentThread</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-psgetcurrentprocessid.md">PsGetCurrentProcessId</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-psgetcurrentthread.md">PsGetCurrentThread</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-pssetcreatethreadnotifyroutine.md">PsSetCreateThreadNotifyRoutine</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PsGetCurrentThreadId routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


---
UID: NF:wdm.KdDisableDebugger
title: KdDisableDebugger function
author: windows-driver-content
description: The KdDisableDebugger routine disables the kernel debugger.
old-location: devtest\kddisabledebugger.htm
old-project: devtest
ms.assetid: 491f1b10-342d-4edf-9b70-732f9d4755f2
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: KdDisableDebugger
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows 2000 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KdDisableDebugger
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

# KdDisableDebugger function



## -description
The <b>KdDisableDebugger</b> routine disables the kernel debugger. 



## -syntax

````
NTSTATUS KdDisableDebugger(void);
````


## -parameters


## -returns
<b>KdDisableDebugger</b> returns STATUS_SUCCESS if the kernel debugger was successfully disabled. Otherwise, the return value can be one of the following error status codes:

STATUS_ACCESS_DENIED

STATUS_DEBUGGER_INACTIVE

<b>KdDisableDebugger</b> returns STATUS_SUCCESS if the kernel debugger was successfully disabled. Otherwise, the return value can be one of the following error status codes:

STATUS_ACCESS_DENIED

STATUS_DEBUGGER_INACTIVE

<b>KdDisableDebugger</b> returns STATUS_SUCCESS if the kernel debugger was successfully disabled. Otherwise, the return value can be one of the following error status codes:

STATUS_ACCESS_DENIED

STATUS_DEBUGGER_INACTIVE


## -remarks
If the operating system was booted with no debug controls, <b>KdDisableDebugger</b> returns STATUS_DEBUGGER_INACTIVE.

If the kernel debugger is blocked (that is, the <b>KdBlockEnable</b> system variable is set to a value other than <b>FALSE</b>), <b>KdDisableDebugger</b> returns STATUS_ACCESS_DENIED. 

After a caller calls <b>KdDisableDebugger</b> to disable the kernel debugger, the caller can call the <a href="..\wdm\nf-wdm-kdenabledebugger.md">KdEnableDebugger</a> routine to re-enable the kernel debugger.


## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-kdenabledebugger.md">KdEnableDebugger</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [devtest\devtest]:%20KdDisableDebugger routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


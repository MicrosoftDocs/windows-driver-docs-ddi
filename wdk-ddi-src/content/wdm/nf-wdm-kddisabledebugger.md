---
UID: NF:wdm.KdDisableDebugger
title: KdDisableDebugger function
author: windows-driver-content
description: The KdDisableDebugger routine disables the kernel debugger.
old-location: devtest\kddisabledebugger.htm
old-project: devtest
ms.assetid: 491f1b10-342d-4edf-9b70-732f9d4755f2
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: DebugFns_e280d38c-6f87-4540-a782-d7669815a0f5.xml, KdDisableDebugger, KdDisableDebugger routine [Driver Development Tools], devtest.kddisabledebugger, wdm/KdDisableDebugger
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	KdDisableDebugger
product: Windows
targetos: Windows
req.typenames: 
---

# KdDisableDebugger function


## -description


The <b>KdDisableDebugger</b> routine disables the kernel debugger. 


## -parameters






## -returns



<b>KdDisableDebugger</b> returns STATUS_SUCCESS if the kernel debugger was successfully disabled. Otherwise, the return value can be one of the following error status codes:

STATUS_ACCESS_DENIED

STATUS_DEBUGGER_INACTIVE




## -remarks



If the operating system was booted with no debug controls, <b>KdDisableDebugger</b> returns STATUS_DEBUGGER_INACTIVE.

If the kernel debugger is blocked (that is, the <b>KdBlockEnable</b> system variable is set to a value other than <b>FALSE</b>), <b>KdDisableDebugger</b> returns STATUS_ACCESS_DENIED. 

After a caller calls <b>KdDisableDebugger</b> to disable the kernel debugger, the caller can call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548085">KdEnableDebugger</a> routine to re-enable the kernel debugger.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548085">KdEnableDebugger</a>
 

 


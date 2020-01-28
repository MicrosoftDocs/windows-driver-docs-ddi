---
UID: NF:wdm.KdEnableDebugger
title: KdEnableDebugger function (wdm.h)
description: The KdEnableDebugger routine re-enables the kernel debugger after a call to the KdDisableDebugger routine disables the kernel debugger.
old-location: devtest\kdenabledebugger.htm
tech.root: devtest
ms.assetid: 90151c0d-24c9-4304-bdcf-30dc89397905
ms.date: 02/23/2018
ms.keywords: DebugFns_080ae06e-7e0c-45e1-a470-22e99922eb72.xml, KdEnableDebugger, KdEnableDebugger routine [Driver Development Tools], devtest.kdenabledebugger, wdm/KdEnableDebugger
f1_keywords:
 - "wdm/KdEnableDebugger"
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- KdEnableDebugger
product:
- Windows
targetos: Windows
req.typenames: 
---

# KdEnableDebugger function


## -description


The <b>KdEnableDebugger</b> routine re-enables the kernel debugger after a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kddisabledebugger">KdDisableDebugger</a> routine disables the kernel debugger. 


## -returns



<b>KdEnableDebugger</b> returns STATUS_SUCCESS if the kernel debugger was successfully re-enabled. Otherwise, the return value can be one of the following error status codes:S

TATUS_ACCESS_DENIED

STATUS_DEBUGGER_INACTIVE




## -remarks



If the operating system was booted with no debug controls, <b>KdEnableDebugger</b> returns STATUS_DEBUGGER_INACTIVE.

If the kernel debugger is blocked (that is, the <b>KdBlockEnable</b> system variable is set to a value other than <b>FALSE</b>), <b>KdEnableDebugger</b> returns STATUS_ACCESS_DENIED. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kddisabledebugger">KdDisableDebugger</a>
 

 


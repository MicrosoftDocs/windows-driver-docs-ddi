---
UID: NF:wdm.KeAreAllApcsDisabled
title: KeAreAllApcsDisabled function (wdm.h)
description: The KeAreAllApcsDisabled routine indicates whether the calling thread is inside a guarded region or running at IRQL >= APC_LEVEL, which disables all APC delivery.
old-location: kernel\keareallapcsdisabled.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["KeAreAllApcsDisabled function"]
ms.keywords: KeAreAllApcsDisabled, KeAreAllApcsDisabled routine [Kernel-Mode Driver Architecture], k105_91675ec9-bef3-4ef8-9403-14999e018745.xml, kernel.keareallapcsdisabled, wdm/KeAreAllApcsDisabled
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Server 2003 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - KeAreAllApcsDisabled
 - wdm/KeAreAllApcsDisabled
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - KeAreAllApcsDisabled
---

# KeAreAllApcsDisabled function


## -description

The <b>KeAreAllApcsDisabled</b> routine indicates whether the calling thread is inside a guarded region or running at IRQL >= APC_LEVEL, which disables all APC delivery.

## -parameters

## -returns

<b>KeAreAllApcsDisabled</b> returns <b>TRUE</b> if the calling thread is inside a guarded region or running at IRQL >= APC_LEVEL, and <b>FALSE</b> otherwise.

## -remarks

A thread inside a guarded region or running at IRQL >= APC_LEVEL has all APCs disabled, including special kernel APCs.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-keareapcsdisabled">KeAreApcsDisabled</a>

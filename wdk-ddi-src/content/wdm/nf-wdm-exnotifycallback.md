---
UID: NF:wdm.ExNotifyCallback
title: ExNotifyCallback function (wdm.h)
description: The ExNotifyCallback routine causes all callback routines registered for the given object to be called.
old-location: kernel\exnotifycallback.htm
tech.root: kernel
ms.assetid: 5c126639-494d-45b4-81c2-1af6dc773db6
ms.date: 04/30/2018
keywords: ["ExNotifyCallback function"]
ms.keywords: ExNotifyCallback, ExNotifyCallback routine [Kernel-Mode Driver Architecture], k102_befd9baa-99b3-427b-a0c3-4287e5563482.xml, kernel.exnotifycallback, wdm/ExNotifyCallback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.irql: <= DISPATCH_LEVEL (see Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - ExNotifyCallback
 - wdm/ExNotifyCallback
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ExNotifyCallback
---

# ExNotifyCallback function


## -description

The <b>ExNotifyCallback</b> routine causes all callback routines registered for the given object to be called.

## -parameters

### -param CallbackObject 

[in]
A pointer to the callback object for which all registered callback routines will be called.

### -param Argument1 

[in, optional]
Specifies the parameter that is passed as <i>Argument1</i> of the callback routine.

### -param Argument2 

[in, optional]
Specifies the parameter that is passed as <i>Argument2</i> of the callback routine.

## -remarks

Driver writers <u>must not</u> call <b>ExNotifyCallback</b> for any of the system-defined callback objects listed in <b>ExCreateCallback</b>.

The system calls callback routines in order of their registration.

For more information about callback objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/callback-objects">Callback Objects</a>.

Callers of this routine must be running at IRQL <= DISPATCH_LEVEL. The system calls all registered callback routines at the caller's IRQL.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-excreatecallback">ExCreateCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exregistercallback">ExRegisterCallback</a>


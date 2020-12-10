---
UID: NF:wdm.ExUnregisterCallback
title: ExUnregisterCallback function (wdm.h)
description: The ExUnregisterCallback routine removes a callback routine previously registered with a callback object from the list of routines to be called during the notification process.
old-location: kernel\exunregistercallback.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["ExUnregisterCallback function"]
ms.keywords: ExUnregisterCallback, ExUnregisterCallback routine [Kernel-Mode Driver Architecture], k102_981ea9e7-42fc-4c63-9cc9-5d7aa3d35b72.xml, kernel.exunregistercallback, wdm/ExUnregisterCallback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlExApcLte2, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <=APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - ExUnregisterCallback
 - wdm/ExUnregisterCallback
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ExUnregisterCallback
---

# ExUnregisterCallback function


## -description

The <b>ExUnregisterCallback</b> routine removes a callback routine previously registered with a callback object from the list of routines to be called during the notification process.

## -parameters

### -param CallbackRegistration 

[in, out]
Specifies the callback routine to unregister. This must be the value returned by <b>ExRegisterCallback</b> when the callback was registered.

## -remarks

For more information about callback objects, see <a href="/windows-hardware/drivers/kernel/callback-objects">Callback Objects</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-excreatecallback">ExCreateCallback</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exregistercallback">ExRegisterCallback</a>

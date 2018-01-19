---
UID: NF:ntddk.IoUnregisterBootDriverCallback
title: IoUnregisterBootDriverCallback function
author: windows-driver-content
description: The IoUnRegisterBootDriverCallback routine unregisters a previously registered BOOT_DRIVER_CALLBACK_FUNCTION routine.
old-location: kernel\iounregisterbootdrivercallback.htm
old-project: kernel
ms.assetid: 6199672C-A4A4-4ED8-B91E-95D96A472449
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: IoUnregisterBootDriverCallback
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with  Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IoUnRegisterBootDriverCallback
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

# IoUnregisterBootDriverCallback function



## -description
The <b>IoUnRegisterBootDriverCallback</b> routine unregisters a previously registered <b>BOOT_DRIVER_CALLBACK_FUNCTION</b> routine.



## -syntax

````
void IoUnRegisterBootDriverCallback(
  _In_ PVOID CallbackHandle
);
````


## -parameters

### -param CallbackHandle [in]

A handle returned from a previous call to <a href="..\ntddk\nf-ntddk-ioregisterbootdrivercallback.md">IoRegisterBootDriverCallback</a>.


## -returns
None


## -remarks
A driver that calls <a href="..\ntddk\nf-ntddk-ioregisterbootdrivercallback.md">IoRegisterBootDriverCallback</a> must call <b>IoUnRegisterBootDriverCallback</b> before being unloaded.


## -see-also
<dl>
<dt>
<a href="..\ntddk\nf-ntddk-ioregisterbootdrivercallback.md">IoRegisterBootDriverCallback</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoUnRegisterBootDriverCallback routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


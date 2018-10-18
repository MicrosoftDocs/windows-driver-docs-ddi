---
UID: NF:ntddk.IoUnregisterBootDriverCallback
title: IoUnregisterBootDriverCallback function
author: windows-driver-content
description: The IoUnRegisterBootDriverCallback routine unregisters a previously registered BOOT_DRIVER_CALLBACK_FUNCTION routine.
old-location: kernel\iounregisterbootdrivercallback.htm
tech.root: kernel
ms.assetid: 6199672C-A4A4-4ED8-B91E-95D96A472449
ms.date: 4/30/2018
ms.keywords: IoUnRegisterBootDriverCallback, IoUnRegisterBootDriverCallback routine [Kernel-Mode Driver Architecture], IoUnregisterBootDriverCallback, kernel.iounregisterbootdrivercallback, ntddk/IoUnRegisterBootDriverCallback
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with  Windows 8.
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
req.irql: <= APC_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoUnRegisterBootDriverCallback
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoUnregisterBootDriverCallback function


## -description


The <b>IoUnRegisterBootDriverCallback</b> routine unregisters a previously registered <b>[**BOOT_DRIVER_CALLBACK_FUNCTION**](nc-ntddk-boot_driver_callback_function.md)</b> routine.


## -parameters




### -param CallbackHandle [in]

A handle returned from a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/hh439379">IoRegisterBootDriverCallback</a>.


## -returns



None




## -remarks



A driver that calls <a href="https://msdn.microsoft.com/library/windows/hardware/hh439379">IoRegisterBootDriverCallback</a> must call <b>IoUnRegisterBootDriverCallback</b> before being unloaded.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439379">IoRegisterBootDriverCallback</a>
 

 


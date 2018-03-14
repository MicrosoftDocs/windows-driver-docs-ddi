---
UID: NF:ntddk.IoUnregisterBootDriverCallback
title: IoUnregisterBootDriverCallback function
author: windows-driver-content
description: The IoUnRegisterBootDriverCallback routine unregisters a previously registered BOOT_DRIVER_CALLBACK_FUNCTION routine.
old-location: kernel\iounregisterbootdrivercallback.htm
old-project: kernel
ms.assetid: 6199672C-A4A4-4ED8-B91E-95D96A472449
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: IoUnRegisterBootDriverCallback, IoUnRegisterBootDriverCallback routine [Kernel-Mode Driver Architecture], IoUnregisterBootDriverCallback, kernel.iounregisterbootdrivercallback, ntddk/IoUnRegisterBootDriverCallback
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
-	IoUnRegisterBootDriverCallback
product: Windows
targetos: Windows
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

<a href="..\ntddk\nf-ntddk-ioregisterbootdrivercallback.md">IoRegisterBootDriverCallback</a>



 

 



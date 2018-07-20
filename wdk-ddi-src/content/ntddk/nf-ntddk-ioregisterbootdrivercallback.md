---
UID: NF:ntddk.IoRegisterBootDriverCallback
title: IoRegisterBootDriverCallback function
author: windows-driver-content
description: The IoRegisterBootDriverCallback routine registers a BOOT_DRIVER_CALLBACK_FUNCTION routine to be called during the initialization of a boot-start driver and its dependent DLLs.
old-location: kernel\ioregisterbootdrivercallback.htm
tech.root: kernel
ms.assetid: 28BA4B54-F493-4D79-89DF-D890EBCF1E9C
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: IoRegisterBootDriverCallback, IoRegisterBootDriverCallback routine [Kernel-Mode Driver Architecture], kernel.ioregisterbootdrivercallback, ntddk/IoRegisterBootDriverCallback
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoRegisterBootDriverCallback
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoRegisterBootDriverCallback function


## -description


The <b>IoRegisterBootDriverCallback</b> routine registers a <b>[**BOOT_DRIVER_CALLBACK_FUNCTION**](nc-ntddk-boot_driver_callback_function.md)</b> routine to be called during the initialization of a boot-start driver and its dependent DLLs.


## -parameters




### -param CallbackFunction [in]

A pointer to the <b>[**BOOT_DRIVER_CALLBACK_FUNCTION**](nc-ntddk-boot_driver_callback_function.md)</b> routine to be called when initializing a boot-start driver or DLL.


### -param CallbackContext [in, optional]

A driver-defined context to be passed to the <b>[**BOOT_DRIVER_CALLBACK_FUNCTION**](nc-ntddk-boot_driver_callback_function.md)</b> routine pointed to by <i>CallbackFunction</i>.


## -returns



A handle that represents the registration. This handle must be supplied as an input parameter in the call to the  <a href="https://msdn.microsoft.com/library/windows/hardware/hh439394">IoUnRegisterBootDriverCallback</a> routine that unregisters the <b>[**BOOT_DRIVER_CALLBACK_FUNCTION**](nc-ntddk-boot_driver_callback_function.md)</b> routine.




## -remarks



Boot-start drivers must call <a href="https://msdn.microsoft.com/library/windows/hardware/hh439394">IoUnRegisterBootDriverCallback</a> and pass the returned handle to unregister the boot-start driver callback before Windows unloads them.


Any error returned from a status update callback is treated as fatal and leads to a system bug check. Additionally, if an initialize image callback returns an error, the driver's image is treated as unknown.
To be notified of boot-start driver initialization operations, an <i>early launch anti-malware</i> (ELAM) driver can call <b>IoRegisterBootDriverCallback</b> to register a <b>[**BOOT_DRIVER_CALLBACK_FUNCTION**](nc-ntddk-boot_driver_callback_function.md)</b>  routine.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh406352">BDCB_CALLBACK_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406359">BDCB_IMAGE_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439394">IoUnRegisterBootDriverCallback</a>
 

 


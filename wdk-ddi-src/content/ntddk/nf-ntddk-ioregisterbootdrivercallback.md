---
UID: NF:ntddk.IoRegisterBootDriverCallback
title: IoRegisterBootDriverCallback function
author: windows-driver-content
description: The IoRegisterBootDriverCallback routine registers a BOOT_DRIVER_CALLBACK_FUNCTION routine to be called during the initialization of a boot-start driver and its dependent DLLs.
old-location: kernel\ioregisterbootdrivercallback.htm
old-project: kernel
ms.assetid: 28BA4B54-F493-4D79-89DF-D890EBCF1E9C
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.ioregisterbootdrivercallback, IoRegisterBootDriverCallback, ntddk/IoRegisterBootDriverCallback, IoRegisterBootDriverCallback routine [Kernel-Mode Driver Architecture]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoRegisterBootDriverCallback
product: Windows
targetos: Windows
req.typenames: "*PWHEA_RAW_DATA_FORMAT, WHEA_RAW_DATA_FORMAT"
---

# IoRegisterBootDriverCallback function


## -description


The <b>IoRegisterBootDriverCallback</b> routine registers a <b>BOOT_DRIVER_CALLBACK_FUNCTION</b> routine to be called during the initialization of a boot-start driver and its dependent DLLs.


## -syntax


````
PVOID IoRegisterBootDriverCallback(
  _In_     PBOOT_DRIVER_CALLBACK_FUNCTION CallbackFunction,
  _In_opt_ PVOID                          CallbackContext
);
````


## -parameters




### -param CallbackFunction [in]

A pointer to the <b>BOOT_DRIVER_CALLBACK_FUNCTION</b> routine to be called when initializing a boot-start driver or DLL.


### -param CallbackContext [in, optional]

A driver-defined context to be passed to the <b>BOOT_DRIVER_CALLBACK_FUNCTION</b> routine pointed to by <i>CallbackFunction</i>.


## -returns



A handle that represents the registration. This handle must be supplied as an input parameter in the call to the  <a href="..\ntddk\nf-ntddk-iounregisterbootdrivercallback.md">IoUnRegisterBootDriverCallback</a> routine that unregisters the <b>BOOT_DRIVER_CALLBACK_FUNCTION</b> routine.




## -remarks



Boot-start drivers must call <a href="..\ntddk\nf-ntddk-iounregisterbootdrivercallback.md">IoUnRegisterBootDriverCallback</a> and pass the returned handle to unregister the boot-start driver callback before Windows unloads them.

<h3><a id="Boot_Driver_Callback"></a><a id="boot_driver_callback"></a><a id="BOOT_DRIVER_CALLBACK"></a>Boot Driver Callback</h3>
A boot-start driver's <b>BOOT_DRIVER_CALLBACK_FUNCTION</b> routine can monitor boot-start driver initialization events and return data to the kernel to enable the kernel to decide whether to initialize each boot-start driver. The function prototype to register a boot-start driver callback routine is as follows.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
VOID
BOOT_DRIVER_CALLBACK_FUNCTION (
    _in_opt_ PVOID CallbackContext,
    _in_ BDCB_CALLBACK_TYPE CallbackType,
    _in_opt_ PBDCB_IMAGE_INFORMATION CallbackTypeContext
    );</pre>
</td>
</tr>
</table></span></div>
The boot-start callback parameters are as follows:



<b>Return Value</b>

If the <b>BOOT_DRIVER_CALLBACK_FUNCTION</b> routine returns STATUS_SUCCESS, the boot-start driver was able to perform all necessary actions in response to the specific callback.

Any error returned from a status update callback is treated as fatal and leads to a system bug check.

If an initialize image callback returns an error,  the driver's image is treated as unknown.

<b>Remarks</b>

To be notified of boot-start driver initialization operations, an <i>early launch anti-malware</i> (ELAM) driver can call <b>IoRegisterBootDriverCallback</b> to register a <b>BOOT_DRIVER_CALLBACK_FUNCTION</b>  routine.




## -see-also

<a href="..\ntddk\ns-ntddk-_bdcb_image_information.md">BDCB_IMAGE_INFORMATION</a>



<a href="..\ntddk\ne-ntddk-_bdcb_callback_type.md">BDCB_CALLBACK_TYPE</a>



<a href="..\ntddk\nf-ntddk-iounregisterbootdrivercallback.md">IoUnRegisterBootDriverCallback</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoRegisterBootDriverCallback routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


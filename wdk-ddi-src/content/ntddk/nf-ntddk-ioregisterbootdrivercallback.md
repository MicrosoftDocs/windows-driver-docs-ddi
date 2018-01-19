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
ms.keywords: IoRegisterBootDriverCallback
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
req.alt-api: IoRegisterBootDriverCallback
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

A boot-start driver's <b>BOOT_DRIVER_CALLBACK_FUNCTION</b> routine can monitor boot-start driver initialization events and return data to the kernel to enable the kernel to decide whether to initialize each boot-start driver. The function prototype to register a boot-start driver callback routine is as follows.

The boot-start callback parameters are as follows:



The value that the driver passed as the <i>CallbackContext</i> parameter to <b>IoRegisterBootDriverCallback</b> when it registered this <b>BOOT_DRIVER_CALLBACK_FUNCTION</b>  routine.

A <a href="..\ntddk\ne-ntddk-_bdcb_callback_type.md">BDCB_CALLBACK_TYPE</a> enumeration value that either identifies the status of boot-start driver initialization or indicates that a boot-start driver is about to be initialized.

A pointer to a structure that contains information that is specific to the type of callback. The structure type depends on the value passed for <i>CallbackType</i>, as shown in the following table.

<b>BdCbStatusUpdate</b>

<b>BDCB_STATUS_UPDATE_TYPE</b>

<b>BdCbInitializeImage</b>

<b>BDCB_CLASSIFICATION</b>

<b>Return Value</b>

If the <b>BOOT_DRIVER_CALLBACK_FUNCTION</b> routine returns STATUS_SUCCESS, the boot-start driver was able to perform all necessary actions in response to the specific callback.

Any error returned from a status update callback is treated as fatal and leads to a system bug check.

If an initialize image callback returns an error,  the driver's image is treated as unknown.

<b>Remarks</b>

To be notified of boot-start driver initialization operations, an <i>early launch anti-malware</i> (ELAM) driver can call <b>IoRegisterBootDriverCallback</b> to register a <b>BOOT_DRIVER_CALLBACK_FUNCTION</b>  routine.


## -see-also
<dl>
<dt>
<a href="..\ntddk\nf-ntddk-iounregisterbootdrivercallback.md">IoUnRegisterBootDriverCallback</a>
</dt>
<dt>
<a href="..\ntddk\ne-ntddk-_bdcb_callback_type.md">BDCB_CALLBACK_TYPE</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk-_bdcb_image_information.md">BDCB_IMAGE_INFORMATION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoRegisterBootDriverCallback routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


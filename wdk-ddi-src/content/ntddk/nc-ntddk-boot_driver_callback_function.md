---
UID: NC:ntddk.BOOT_DRIVER_CALLBACK_FUNCTION
title: BOOT_DRIVER_CALLBACK_FUNCTION
author: windows-driver-content
description: 
ms.assetid: 00658a7e-2c8f-44cb-aac3-97c36c39f988
ms.date: 
ms.topic: callback
req.header: ntddk.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: PASSIVE_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
-	apiref
api_type: 
-	UserDefined
api_location: 
-	ntddk.h
api_name: 
-	BOOT_DRIVER_CALLBACK_FUNCTION
product:
-	Windows
targetos: Windows
---

# BOOT_DRIVER_CALLBACK_FUNCTION callback function

## -description

A boot-start driver's BOOT_DRIVER_CALLBACK_FUNCTION routine can monitor boot-start driver initialization events and return data to the kernel to enable the kernel to decide whether to initialize each boot-start driver. The function prototype to register a boot-start driver callback routine is as follows.

## -prototype

```
//Declaration

BOOT_DRIVER_CALLBACK_FUNCTION BootDriverCallbackFunction; 

// Definition

VOID BootDriverCallbackFunction 
(
	PVOID CallbackContext
	BDCB_CALLBACK_TYPE Classification
	PBDCB_IMAGE_INFORMATION ImageInformation
)
{...}

```

## -parameters

### -param CallbackContext
The value that the driver passed as the _CallbackContext_ parameter to [**IoRegisterBootDriverCallback**](nf-ntddk-ioregisterbootdrivercallback.md) when it registered this BOOT_DRIVER_CALLBACK_FUNCTION implementation.

### -param Classification
A [**BDCB_CALLBACK_TYPE**](ne-ntddk-_bdcb_callback_type.md) enumeration value that either identifies the status of boot-start driver initialization or indicates that a boot-start driver is about to be initialized.

### -param ImageInformation
A pointer to a [**BDCB_IMAGE_INFORMATION**](ns-ntddk-_bdcb_image_information.md) structure that contains information that is specific to the type of callback. The structure type depends on the value passed for CallbackType, as shown in the following table.

| Value of CallbackType | Corresponding structure to use |
| --------------------- | ------------------------------ |
| BdCbStatusUpdate      | BDCB_STATUS_UPDATE_TYPE        |
| BdCbInitializeImage   | BDCB_CLASSIFICATION            |
 



## -returns

If the **BOOT_DRIVER_CALLBACK_FUNCTION** routine returns STATUS_SUCCESS, the boot-start driver was able to perform all necessary actions in response to the specific callback.

Any error returned from a status update callback is treated as fatal and leads to a system bug check.

If an initialize image callback returns an error, the driver's image is treated as unknown.


## -remarks

To be notified of boot-start driver initialization operations, an early launch anti-malware (ELAM) driver can call [**IoRegisterBootDriverCallback**](nf-ntddk-ioregisterbootdrivercallback.md). To unregister, call [**IoUnRegisterBootDriverCallback**](nf-ntddk-iounregisterbootdrivercallback.md).


## -see-also
[**IoRegisterBootDriverCallback**](nf-ntddk-ioregisterbootdrivercallback.md)

[**IoUnregisterBootDriverCallback**](nf-ntddk-iounregisterbootdrivercallback.md)

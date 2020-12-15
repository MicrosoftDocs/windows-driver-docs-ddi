---
UID: NF:usbdlib.USBD_GetPdoRegistryParameter
title: USBD_GetPdoRegistryParameter function (usbdlib.h)
description: The USBD_GetPdoRegistryParameter routine retrieves the value from the specified key in the USB device's hardware registry.
old-location: buses\usbd_getpdoregistryparameter.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["USBD_GetPdoRegistryParameter function"]
ms.keywords: USBD_GetPdoRegistryParameter, USBD_GetPdoRegistryParameter routine [Buses], buses.usbd_getpdoregistryparameter, usbdlib/USBD_GetPdoRegistryParameter, usbfunc_b85b350e-68ad-4256-b4df-f61ea0367b62.xml
req.header: usbdlib.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: 
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
req.lib: Usbd.lib
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - USBD_GetPdoRegistryParameter
 - usbdlib/USBD_GetPdoRegistryParameter
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - usbd.lib
 - usbd.dll
api_name:
 - USBD_GetPdoRegistryParameter
---

# USBD_GetPdoRegistryParameter function


## -description

The <b>USBD_GetPdoRegistryParameter</b> routine retrieves the value from the  specified key in the USB device's hardware registry.

## -parameters

### -param PhysicalDeviceObject 

[in]
Specifies the device object for the USB device.

### -param ParameterLength 

[in]
Size, in bytes, of the buffer that is pointed to by <i>Parameter</i>.

### -param KeyName 

[in]
Pointer to a string containing the name of the registry key.

### -param KeyNameLength 

[in]
Size, in bytes, of the buffer that is pointed to by <i>KeyName</i>.

### -param Parameter 

[in, out]
Pointer to a caller-allocated buffer that receives the registry value.

## -returns

The <b>USBD_GetPdoRegistryParameter</b> returns STATUS_SUCCESS when the operation succeeds or an appropriate error status when the operation fails.

## -see-also

<a href="/windows-hardware/drivers/ddi/_usbref/">USB device driver programming reference</a>

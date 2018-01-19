---
UID: NF:usbcamdi.USBCAMD_GetRegistryKeyValue
title: USBCAMD_GetRegistryKeyValue function
author: windows-driver-content
description: The USBCAMD_GetRegistryKeyValue function retrieves the device-instance-specific registry key value.
old-location: stream\usbcamd_getregistrykeyvalue.htm
old-project: stream
ms.assetid: c3512a79-884f-4f38-9942-63a4a464585c
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: USBCAMD_GetRegistryKeyValue
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: usbcamdi.h
req.include-header: Usbcamdi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: USBCAMD_GetRegistryKeyValue
req.alt-loc: usbcamd2.lib,usbcamd2.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Usbcamd2.lib
req.dll: 
req.irql: 
req.typenames: USB_BUS_INTERFACE_USBDI_V3, *PUSB_BUS_INTERFACE_USBDI_V3
req.product: Windows 10 or later.
---

# USBCAMD_GetRegistryKeyValue function



## -description
The <b>USBCAMD_GetRegistryKeyValue</b> function retrieves the device-instance-specific registry key value.



## -syntax

````
NTSTATUS USBCAMD_GetRegistryKeyValue(
  _In_ HANDLE Handle,
  _In_ PWCHAR KeyNameString,
  _In_ ULONG  KeyNameStringLength,
  _In_ PVOID  Data,
  _In_ ULONG  DataLength
);
````


## -parameters

### -param Handle [in]

Handle to a valid and open device registry key.


### -param KeyNameString [in]

Pointer to the string buffer describing the key type.


### -param KeyNameStringLength [in]

Specifies the length, in characters, of <i>KeyNameString</i>.


### -param Data [in]

Pointer to a caller-specified value or structure.


### -param DataLength [in]

Specifies the length, in bytes, of the value or structure at <i>Data.</i>


## -returns
<b>USBCAMD_GetRegistryKeyValue </b>returns STATUS_SUCCESS if the call was successful. Other possible error codes include:
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>There was insufficient memory to continue.

 


## -remarks

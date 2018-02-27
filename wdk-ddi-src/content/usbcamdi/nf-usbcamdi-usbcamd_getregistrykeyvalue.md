---
UID: NF:usbcamdi.USBCAMD_GetRegistryKeyValue
title: USBCAMD_GetRegistryKeyValue function
author: windows-driver-content
description: The USBCAMD_GetRegistryKeyValue function retrieves the device-instance-specific registry key value.
old-location: stream\usbcamd_getregistrykeyvalue.htm
old-project: stream
ms.assetid: c3512a79-884f-4f38-9942-63a4a464585c
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: USBCAMD_GetRegistryKeyValue, USBCAMD_GetRegistryKeyValue function [Streaming Media Devices], stream.usbcamd_getregistrykeyvalue, usbcamdi/USBCAMD_GetRegistryKeyValue, usbcmdpr_f93ab3a6-f063-4c69-819d-1aed77b8efe6.xml
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	usbcamd2.lib
-	usbcamd2.dll
api_name:
-	USBCAMD_GetRegistryKeyValue
product: Windows
targetos: Windows
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

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
</td>
<td width="60%">
There was insufficient memory to continue.

</td>
</tr>
</table>
 




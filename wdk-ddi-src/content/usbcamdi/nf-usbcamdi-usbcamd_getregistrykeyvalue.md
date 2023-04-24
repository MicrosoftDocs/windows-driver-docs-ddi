---
UID: NF:usbcamdi.USBCAMD_GetRegistryKeyValue
title: USBCAMD_GetRegistryKeyValue function (usbcamdi.h)
description: The USBCAMD_GetRegistryKeyValue function retrieves the device-instance-specific registry key value.
tech.root: stream
ms.date: 03/08/2023
keywords: ["USBCAMD_GetRegistryKeyValue function"]
ms.keywords: USBCAMD_GetRegistryKeyValue, USBCAMD_GetRegistryKeyValue function [Streaming Media Devices], stream.usbcamd_getregistrykeyvalue, usbcamdi/USBCAMD_GetRegistryKeyValue, usbcmdpr_f93ab3a6-f063-4c69-819d-1aed77b8efe6.xml
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
targetos: Windows
req.typenames: 
f1_keywords:
 - USBCAMD_GetRegistryKeyValue
 - usbcamdi/USBCAMD_GetRegistryKeyValue
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - usbcamd2.lib
 - usbcamd2.dll
api_name:
 - USBCAMD_GetRegistryKeyValue
---

## -description

The **USBCAMD_GetRegistryKeyValue** function retrieves the device-instance-specific registry key value.

## -parameters

### -param Handle [in]

Handle to a valid and open device registry key.

### -param KeyNameString [in]

Pointer to the string buffer describing the key type.

### -param KeyNameStringLength [in]

Specifies the length, in characters, of *KeyNameString*.

### -param Data [in]

Pointer to a caller-specified value or structure.

### -param DataLength [in]

Specifies the length, in bytes, of the value or structure at *Data.*

## -returns

**USBCAMD_GetRegistryKeyValue** returns STATUS_SUCCESS if the call was successful.

Other possible error codes include:

| Return code | Description |
|---|---|
| **STATUS_NO_MEMORY** | There was insufficient memory to continue. |

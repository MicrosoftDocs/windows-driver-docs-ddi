---
UID: NF:dispmprt.DlSetRegistryParameters
title: DlSetRegistryParameters function
author: windows-driver-content
description: Writes information under the adapter key in the registry.
tech.root: display
ms.assetid: ab2d727f-c057-4a8d-9ff6-572a9f81f50e
ms.author: windowsdriverdev
ms.date: 04/04/2019 
ms.topic: function
ms.keywords: DlSetRegistryParameters
req.header: dispmprt.h
req.include-header:
req.target-type:
req.target-min-winverclnt: 
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- DllExport
api_location: 
- Displib.lib
- Displib.dll
api_name: 
- DlSetRegistryParameters
product: 
- Windows
targetos: Windows

ms.custom: 19H1
---

# DlSetRegistryParameters function


## -description

Writes information under the adapter key in the registry.

## -parameters

### -param DeviceHandle

A handle that represents a display adapter.

### -param ValueName

Pointer to a buffer containing a null-terminated Unicode string that names the value entry for which data is being written in the registry.

### -param ValueData

Pointer to a buffer containing the values to be written for the *ValueName* entry.

### -param ValueLength

Specifies the size, in bytes, of the data to be written to the registry.


## -returns

This function returns VP_STATUS.

## -remarks

## -see-also

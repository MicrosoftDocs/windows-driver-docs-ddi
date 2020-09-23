---
UID: NF:dispmprt.DlGetRegistryParameters
title: DlGetRegistryParameters function
description: Retrieves device-specific configuration information under the adapter key in the registry at startup.
tech.root: display
ms.assetid: 33f7e458-2da9-43e4-a335-4e27e2ef1ac6
ms.author: windowsdriverdev
ms.date: 04/04/2019
keywords: ["DlGetRegistryParameters function"]
ms.keywords: DlGetRegistryParameters
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
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - DlGetRegistryParameters
 - dispmprt/DlGetRegistryParameters
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - Displib.lib
 - Displib.dll
api_name:
 - DlGetRegistryParameters
product:
 - Windows
dev_langs:
 - c++
---

# DlGetRegistryParameters function


## -description

Retrieves device-specific configuration information under the adapter key in the registry at startup.

## -parameters

### -param DeviceHandle

A handle that represents a display adapter.

### -param ParameterName

Pointer to a NULL-terminated Unicode string that names the value entry to be retrieved from the registry.

### -param IsParameterFileName

If the value is TRUE, the data value normally returned is treated as a file name.

### -param CallbackRoutine

### -param Context

Pointer to a caller-determined context parameter.

## -returns

This function returns VP_STATUS.

## -remarks

## -see-also


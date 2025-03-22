---
UID: NF:storport.StorPortReadRegistryKey
tech.root: storage
title: StorPortReadRegistryKey
ms.date: 04/02/2024
targetos: Windows
description: The StorPortReadRegistryKey function is used by the miniport to read the specified registry key. The caller provides the absolute path to the key to be read.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: storport.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - StorPortReadRegistryKey
f1_keywords:
 - StorPortReadRegistryKey
 - storport/StorPortReadRegistryKey
dev_langs:
 - c++
helpviewer_keywords:
 - StorPortReadRegistryKey
---

# StorPortReadRegistryKey function (storport.h)

## -description

The **StorPortReadRegistryKey** function is used by the miniport to read the specified registry key. The caller provides the absolute path to the key to be read.

## -parameters

### -param HwDeviceExtension

A pointer to the hardware device extension. This is specific to the miniport driver instance.

### -param AbsolutePath

The absolute path to the key to be read.

### -param KeyName

The key path under the absolute path.

### -param ValueType

The type of the registry key value in REG_XXXX format. Currently, only REG_DWORD value type is supported.

### -param ValueData

Pointer to the data buffer to receive the registry key value.

### -param ValueDataLength

The size of the *ValueData*, in bytes.

## -returns

Returns a STOR_STATUS code as defined in storport.h.

## -remarks

## -see-also

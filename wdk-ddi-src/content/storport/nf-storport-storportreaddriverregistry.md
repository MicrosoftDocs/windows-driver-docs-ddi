---
UID: NF:storport.StorPortReadDriverRegistry
tech.root: storage
title: StorPortReadDriverRegistry
ms.date: 04/02/2024
targetos: Windows
description: The StorPortReadDriverRegistry function is used by the miniport to read the registry data for a given driver object.
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
 - StorPortReadDriverRegistry
f1_keywords:
 - StorPortReadDriverRegistry
 - storport/StorPortReadDriverRegistry
dev_langs:
 - c++
helpviewer_keywords:
 - StorPortReadDriverRegistry
---

# StorPortReadDriverRegistry function (storport.h)

## -description

The **StorPortReadDriverRegistry** function is used by the miniport to read the registry data for a given driver object.

## -parameters

### -param DriverObject

The driver object for which registry data is to be read.

### -param ValueName

The name of the registry data to be returned.

### -param ValueDataLength

The size, in bytes, of the buffer provided for the returned data in the *ValueData* parameter.

### -param ValueData

The buffer for the retrieved data.

## -returns

Returns TRUE if the registry data was read and copied into buffer successfully, otherwise returns FALSE.

## -remarks

The values are located under the driver's service key, for example, HKLM\System\CurrentControlSet\Services\\<*DriverName*>\\<*ValueName*>. The value can be any REG_XXXX type.

## -see-also

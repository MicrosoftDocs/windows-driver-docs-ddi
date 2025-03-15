---
UID: NF:ntifs.REFS_VOLUME_DATA_BUFFER_CONTAINS_DRIVER_VERSION
tech.root: ifsk
title: REFS_VOLUME_DATA_BUFFER_CONTAINS_DRIVER_VERSION
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the REFS_VOLUME_DATA_BUFFER_CONTAINS_DRIVER_VERSION macro.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ntifs.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 8
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
 - ntifs.h
api_name:
 - REFS_VOLUME_DATA_BUFFER_CONTAINS_DRIVER_VERSION
f1_keywords:
 - REFS_VOLUME_DATA_BUFFER_CONTAINS_DRIVER_VERSION
 - ntifs/REFS_VOLUME_DATA_BUFFER_CONTAINS_DRIVER_VERSION
dev_langs:
 - c++
helpviewer_keywords:
 - REFS_VOLUME_DATA_BUFFER_CONTAINS_DRIVER_VERSION
---

## -description

The **REFS_VOLUME_DATA_BUFFER_CONTAINS_DRIVER_VERSION** macro determines whether a [**REFS_VOLUME_DATA_BUFFER**](ns-ntifs-refs_volume_data_buffer.md) structure contains valid driver version information.

## -parameters

### -param VOLUME_DATA_BUFFER

Pointer to a [**REFS_VOLUME_DATA_BUFFER**](ns-ntifs-refs_volume_data_buffer.md) structure that is being checked for the presence of driver version fields.

## -remarks

This macro helps maintain compatibility with different versions of the [**REFS_VOLUME_DATA_BUFFER**](ns-ntifs-refs_volume_data_buffer.md) structure, especially when new fields are added in later versions.  

## -see-also

[**REFS_VOLUME_DATA_BUFFER**](ns-ntifs-refs_volume_data_buffer.md)

---
UID: NF:storport.StorPortGetProcessorCount
tech.root: storage
title: StorPortGetProcessorCount
ms.date: 07/24/2024
targetos: Windows
description: Learn more about the StorPortGetProcessorCount function.
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
req.target-min-winverclnt: Windows 10, version 1709
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
 - StorPortGetProcessorCount
f1_keywords:
 - StorPortGetProcessorCount
 - storport/StorPortGetProcessorCount
dev_langs:
 - c++
helpviewer_keywords:
 - StorPortGetProcessorCount
---

## -description

The **StorPortGetProcessorCount** routine returns the number of active logical processors in the system.

## -parameters

### -param HwDeviceExtension

[in] Pointer to the hardware device extension for the host bus adapter (HBA).

### -param ProcessorCount

[out] Pointer to the location in which the routine returns the number of active logical processors in the system.

## -returns

**StorPortGetProcessorCount** returns one of the following STOR_STATUS codes:

| Return code | Description |
| ----------- | ----------- |
| **STOR_STATUS_NOT_IMPLEMENTED** | This function is not implemented on the active operating system. |
| **STOR_STATUS_SUCCESS** | The operation was successful. |
| **STOR_STATUS_INVALID_PARAMETER** | The operation fails with this return value if one or more of the parameters are invalid. |

## -remarks

For information about active logical processors, see [**KeQueryActiveProcessorCountEx**](../wdm/nf-wdm-kequeryactiveprocessorcountex.md).

## -see-also

[**StorPortGetCurrentProcessorNumber**](nf-storport-storportgetcurrentprocessornumber.md)

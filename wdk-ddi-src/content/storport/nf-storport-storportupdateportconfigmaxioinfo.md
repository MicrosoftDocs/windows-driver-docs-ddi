---
UID: NF:storport.StorPortUpdatePortConfigMaxIOInfo
tech.root: storage
title: StorPortUpdatePortConfigMaxIOInfo
ms.date: 08/05/2024
targetos: Windows
description: Learn more about the StorPortUpdatePortConfigMaxIOInfo function.
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
req.target-min-winverclnt: Windows 10, version 1809
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
 - StorPortUpdatePortConfigMaxIOInfo
f1_keywords:
 - StorPortUpdatePortConfigMaxIOInfo
 - storport/StorPortUpdatePortConfigMaxIOInfo
dev_langs:
 - c++
helpviewer_keywords:
 - StorPortUpdatePortConfigMaxIOInfo
---

## -description

A miniport calls **StorPortUpdatePortConfigMaxIOInfo** to update the maximum IOs and maximum IOs per LUN supported by an adapter.

## -parameters

### -param HwDeviceExtension

[in] A pointer to miniport's device extension.

### -param MaxIoCount

[in] Maximum number of outstanding I/O operations supported by the adapter.

### -param MaxIosPerLun

[in] Maximum number of outstanding I/O operations per LUN supported by the adapter.

## -returns

**StorPortUpdatePortConfigMaxIOInfo** returns STOR_STATUS_SUCCESS upon success. Otherwise, it returns one of the following values:

| Value | Description |
| ----- | ----------- |
| STOR_STATUS_NOT_IMPLEMENTED        | The function was called on an OS version that doesn't support it. |
| STOR_STATUS_INVALID_PARAMETER      | There is an invalid parameter. |
| STOR_STATUS_INVALID_DEVICE_REQUEST | The function was called outside of [**HwInitialize**](nc-storport-hw_initialize.md)/[**HwPassiveInitRoutine**](nc-storport-hw_passive_initialize_routine.md). |

## -remarks

**StorPortUpdatePortConfigMaxIOInfo** is valid only within a [**HwInitialize**](nc-storport-hw_initialize.md)/[**HwPassiveInitRoutine**](nc-storport-hw_passive_initialize_routine.md) callback and has effect only during adapter initialization.

## -see-also

[**HwInitialize**](nc-storport-hw_initialize.md)

[**HwPassiveInitRoutine**](nc-storport-hw_passive_initialize_routine.md)

[**PORT_CONFIGURATION_INFORMATION**](ns-storport-_port_configuration_information.md)

[**StorPortUpdateAdapterMaxIO**](nf-storport-storportupdateadaptermaxio.md)

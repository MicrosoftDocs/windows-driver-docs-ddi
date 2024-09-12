---
UID: NF:storport.StorPortUpdateAdapterMaxIO
title: StorPortUpdateAdapterMaxIO function (storport.h)
description: Learn more about the StorPortUpdateAdapterMaxIO function.
tech.root: storage
ms.date: 08/05/2024
req.header: storport.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - StorPortUpdateAdapterMaxIO
 - storport/StorPortUpdateAdapterMaxIO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Storport.h
api_name:
 - StorPortUpdateAdapterMaxIO
---

# StorPortUpdateAdapterMaxIO function

## -description

A miniport calls **StorPortUpdateAdapterMaxIO** to update the maximum number of outstanding I/O operations supported by an adapter.

## -parameters

### -param HwDeviceExtension

[in] A pointer to miniport's device extension.

### -param MaxIoCount

[in] Maximum number of outstanding I/O operations supported by the adapter.

## -returns

**StorPortUpdateAdapterMaxIO** returns STOR_STATUS_SUCCESS upon success. Otherwise, it returns one of the following values:

| Value | Description |
| ----- | ----------- |
| STOR_STATUS_NOT_IMPLEMENTED        | The function was called on an OS version that doesn't support it. |
| STOR_STATUS_INVALID_PARAMETER      | There is an invalid parameter. |
| STOR_STATUS_INVALID_DEVICE_REQUEST | The function was called outside of [**HwInitialize**](nc-storport-hw_initialize.md)/[**HwPassiveInitRoutine**](nc-storport-hw_passive_initialize_routine.md). |

## -remarks

**StorPortUpdateAdapterMaxIO** is valid only within a [**HwInitialize**](nc-storport-hw_initialize.md)/[**HwPassiveInitRoutine**](nc-storport-hw_passive_initialize_routine.md) callback and has effect only during adapter initialization.

## -see-also

[**HwInitialize**](nc-storport-hw_initialize.md)

[**HwPassiveInitRoutine**](nc-storport-hw_passive_initialize_routine.md)

[**PORT_CONFIGURATION_INFORMATION**](ns-storport-_port_configuration_information.md)

[**StorPortUpdatePortConfigMaxIOInfo**](nf-storport-storportupdateportconfigmaxioinfo.md)

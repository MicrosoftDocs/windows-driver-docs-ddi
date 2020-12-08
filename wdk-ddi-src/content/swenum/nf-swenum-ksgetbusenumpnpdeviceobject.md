---
UID: NF:swenum.KsGetBusEnumPnpDeviceObject
title: KsGetBusEnumPnpDeviceObject function (swenum.h)
description: The KsGetBusEnumPnpDeviceObject function retrieves the Plug and Play device object attached to the given device object.
old-location: stream\ksgetbusenumpnpdeviceobject.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KsGetBusEnumPnpDeviceObject function"]
ms.keywords: KsGetBusEnumPnpDeviceObject, KsGetBusEnumPnpDeviceObject function [Streaming Media Devices], ksfunc_246a7c6e-ef5a-4cf4-a05a-70a499a487cb.xml, stream.ksgetbusenumpnpdeviceobject, swenum/KsGetBusEnumPnpDeviceObject
req.header: swenum.h
req.include-header: Swenum.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - KsGetBusEnumPnpDeviceObject
 - swenum/KsGetBusEnumPnpDeviceObject
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsGetBusEnumPnpDeviceObject
---

# KsGetBusEnumPnpDeviceObject function


## -description

<i>This function is intended for internal use only.</i>

The <b>KsGetBusEnumPnpDeviceObject</b> function retrieves the Plug and Play device object attached to the given device object.

## -parameters

### -param DeviceObject 

[in]
Pointer to the device object from which to retrieve the Plug and Play device object.

### -param PnpDeviceObject 

[out]
Pointer to the device object to receive the Plug and Play device object pointer.

## -returns

Returns STATUS_SUCCESS if successful, or STATUS_INVALID_PARAMETER if <i>DeviceObject</i> does not contain a device extension, or if the device extension specified in <i>DeviceObject </i>is not that of an FDO.


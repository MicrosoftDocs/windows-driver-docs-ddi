---
UID: NF:ks.KsDispatchInvalidDeviceRequest
title: KsDispatchInvalidDeviceRequest function (ks.h)
description: The KsDispatchInvalidDeviceRequest function is used in KSDISPATCH_TABLE entries that are not handled and that need to return STATUS_INVALID_DEVICE_REQUEST.
old-location: stream\ksdispatchinvaliddevicerequest.htm
tech.root: stream
ms.assetid: 7c30bc5b-2bd5-4db9-acaf-0c0347035ae3
ms.date: 04/23/2018
keywords: ["KsDispatchInvalidDeviceRequest function"]
ms.keywords: KsDispatchInvalidDeviceRequest, KsDispatchInvalidDeviceRequest function [Streaming Media Devices], ks/KsDispatchInvalidDeviceRequest, ksfunc_9be97c86-7505-4192-8a61-8280fca7ba0c.xml, stream.ksdispatchinvaliddevicerequest
req.header: ks.h
req.include-header: Ks.h
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
 - KsDispatchInvalidDeviceRequest
 - ks/KsDispatchInvalidDeviceRequest
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsDispatchInvalidDeviceRequest
---

# KsDispatchInvalidDeviceRequest function


## -description

The <b>KsDispatchInvalidDeviceRequest</b> function is used in KSDISPATCH_TABLE entries that are not handled and that need to return STATUS_INVALID_DEVICE_REQUEST.

## -parameters

### -param DeviceObject 

[in]
Specifies the device object associated with the IRP.

### -param Irp 

[in]
Specifies the IRP that is not being handled.

## -returns

The <b>KsDispatchInvalidDeviceRequest</b> function returns STATUS_INVALID_DEVICE_REQUEST and completes the IRP.

## -remarks

The <b>KsDispatchInvalidDeviceRequest</b> function is needed because the dispatch table for an opened instance of a device may not handle a specific major function that another opened instance needs to handle. Therefore, the function pointer in the driver object must always point to a function that calls a dispatch table entry.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksdispatchfastiodevicecontrolfailure">KsDispatchFastIoDeviceControlFailure</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksdispatchfastreadfailure">KsDispatchFastReadFailure</a>



<a href="https://docs.microsoft.com/previous-versions/ff561706(v=vs.85)">KsDispatchFastWriteFailure</a>


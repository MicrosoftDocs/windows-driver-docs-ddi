---
UID: NF:ks.KsSetDevicePnpAndBaseObject
title: KsSetDevicePnpAndBaseObject function (ks.h)
description: The KsSetDevicePnpAndBaseObject function sets the PnP device object in the device header, which is the next device object on the PnP stack and is the device object that PnP requests are forwarded to if KsDefaultDispatchPnp is used.
tech.root: stream
ms.date: 07/13/2022
keywords: ["KsSetDevicePnpAndBaseObject function"]
ms.keywords: KsSetDevicePnpAndBaseObject, KsSetDevicePnpAndBaseObject function [Streaming Media Devices], ks/KsSetDevicePnpAndBaseObject, ksfunc_eff06a34-a458-4426-972c-6a0fbf0f7846.xml, stream.kssetdevicepnpandbaseobject
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
 - KsSetDevicePnpAndBaseObject
 - ks/KsSetDevicePnpAndBaseObject
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsSetDevicePnpAndBaseObject
---

## -description

The **KsSetDevicePnpAndBaseObject** function sets the PnP device object in the device header, which is the next device object on the PnP stack and is the device object that PnP requests are forwarded to if **KsDefaultDispatchPnp** is used.

## -parameters

### -param Header [in]

Points to a header previously allocated by **KsAllocateDeviceHeader** in which to put the PnP device object.

### -param PnpDeviceObject [in]

Specifies the PnP device object to place in the device header, overwriting any previously set device object.

### -param BaseObject

Specifies the base device object to which this device header is attached. This must be set if **KsRecalculateStackDepth** is used.

## -returns

None

## -see-also

[KsAllocateDeviceHeader](./nf-ks-ksallocatedeviceheader.md)

[KsRecalculateStackDepth](./nf-ks-ksrecalculatestackdepth.md)
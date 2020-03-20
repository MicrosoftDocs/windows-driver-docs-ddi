---
UID: NF:ks.KsSetDevicePnpAndBaseObject
title: KsSetDevicePnpAndBaseObject function (ks.h)
description: The KsSetDevicePnpAndBaseObject function sets the PnP device object in the device header, which is the next device object on the PnP stack and is the device object that PnP requests are forwarded to if KsDefaultDispatchPnp is used.
old-location: stream\kssetdevicepnpandbaseobject.htm
tech.root: stream
ms.assetid: 269bbb79-c730-4b78-bf46-d502f23f039b
ms.date: 04/23/2018
keywords: ["KsSetDevicePnpAndBaseObject function"]
ms.keywords: KsSetDevicePnpAndBaseObject, KsSetDevicePnpAndBaseObject function [Streaming Media Devices], ks/KsSetDevicePnpAndBaseObject, ksfunc_eff06a34-a458-4426-972c-6a0fbf0f7846.xml, stream.kssetdevicepnpandbaseobject
f1_keywords:
 - "ks/KsSetDevicePnpAndBaseObject"
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
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsSetDevicePnpAndBaseObject function


## -description


The <b>KsSetDevicePnpAndBaseObject</b> function sets the PnP device object in the device header, which is the next device object on the PnP stack and is the device object that PnP requests are forwarded to if <b>KsDefaultDispatchPnp</b> is used.


## -parameters




### -param Header [in]

Points to a header previously allocated by <b>KsAllocateDeviceHeader</b> in which to put the PnP device object.


### -param PnpDeviceObject [in]

Specifies the PnP device object to place in the device header, overwriting any previously set device object.


### -param BaseObject






#### - BaseDevice [in]

Specifies the base device object to which this device header is attached. This must be set if <b>KsRecalculateStackDepth</b> is used.


## -returns



None




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksallocatedeviceheader">KsAllocateDeviceHeader</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksrecalculatestackdepth">KsRecalculateStackDepth</a>
 

 


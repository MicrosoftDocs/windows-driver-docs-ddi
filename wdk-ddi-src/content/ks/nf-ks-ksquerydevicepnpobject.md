---
UID: NF:ks.KsQueryDevicePnpObject
title: KsQueryDevicePnpObject function (ks.h)
description: The KsQueryDevicePnpObject function returns the PnP device object that can be stored in the device header. This is the next device object on the PnP stack and is the device object that PnP requests are forwarded to if KsDefaultDispatchPnp is used.
old-location: stream\ksquerydevicepnpobject.htm
tech.root: stream
ms.assetid: 207b776a-8f51-4385-a171-a9d0e84e70b5
ms.date: 04/23/2018
keywords: ["KsQueryDevicePnpObject function"]
ms.keywords: KsQueryDevicePnpObject, KsQueryDevicePnpObject function [Streaming Media Devices], ks/KsQueryDevicePnpObject, ksfunc_dd821abc-bd3b-45e9-a1de-1f9fd201db8e.xml, stream.ksquerydevicepnpobject
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
 - KsQueryDevicePnpObject
 - ks/KsQueryDevicePnpObject
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsQueryDevicePnpObject
---

# KsQueryDevicePnpObject function


## -description

The <b>KsQueryDevicePnpObject</b> function returns the PnP device object that can be stored in the device header. This is the next device object on the PnP stack and is the device object that PnP requests are forwarded to if <b>KsDefaultDispatchPnp</b> is used.

## -parameters

### -param Header 

[in]
Points to a header previously allocated by <a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksallocatedeviceheader">KsAllocateDeviceHeader</a> whose PnP device object is to be returned.

## -returns

The <b>KsQueryDevicePnpObject</b> function returns the previously set PnP device object. If none was set, it returns <b>NULL</b>.

## -see-also

<a href="/previous-versions/ff561665(v=vs.85)">KsDefaultDispatchPnp</a>
---
UID: NF:ks.KsRecalculateStackDepth
title: KsRecalculateStackDepth function (ks.h)
description: The KsRecalculateStackDepth function recalculates the maximum stack depth required by the underlying device object based on all of the objects that have set a target device (they have added themselves to the object list on the underlying device object using the KsSetTargetDeviceObject function). If the PnP device object has been set on the underlying device header using KsSetDevicePnpAndBaseObject, that device is also taken into account when calculating the maximum stack depth.
old-location: stream\ksrecalculatestackdepth.htm
tech.root: stream
ms.assetid: 0b8f23a5-af8a-4b99-8f17-092076523914
ms.date: 04/23/2018
keywords: ["KsRecalculateStackDepth function"]
ms.keywords: KsRecalculateStackDepth, KsRecalculateStackDepth , KsRecalculateStackDepth function [Streaming Media Devices], ks/KsRecalculateStackDepth, ksfunc_745f6176-dc53-467f-885e-028da49b81a1.xml, stream.ksrecalculatestackdepth
f1_keywords:
 - "ks/KsRecalculateStackDepth"
 - "KsRecalculateStackDepth"
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
- KsRecalculateStackDepth
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsRecalculateStackDepth function


## -description


The <b>KsRecalculateStackDepth</b> function recalculates the maximum stack depth required by the underlying device object based on all of the objects that have set a target device (they have added themselves to the object list on the underlying device object using the <b>KsSetTargetDeviceObject</b> function). If the PnP device object has been set on the underlying device header using <b>KsSetDevicePnpAndBaseObject</b>, that device is also taken into account when calculating the maximum stack depth.


## -parameters




### -param Header [in]

Points to a header previously allocated by <b>KsAllocateDeviceHeader</b>.


### -param ReuseStackLocation [in]

If this is set to <b>TRUE</b>, the current stack location is reused when any IRP is forwarded. This means that this object does not require its own stack location when forwarding IRPs and an extra location is not added to the maximum stack size. If set to <b>FALSE</b>, the calculated stack size is incremented by one. If the Pnp object stack is set, the reuse parameter also applies to that stack. Note that <b>KsDefaultDispatchPnp</b> always reuses the current stack location. The minimum stack depth is 1.


## -returns



None




## -remarks



The <b>KsRecalculateStackDepth</b> function assumes that <b>KsSetDevicePnpAndBaseObject</b> has been called on this device header and has assigned a base object whose stack depth is to be recalculated.

This function allows IRPs to be forwarded through an object by ensuring that any IRP allocated on this device will have sufficient stack locations to allow it to be forwarded. Stack depth must be recalculated on a streaming device when the device transitions out of a Stop state. It can also be recalculated when an object is freed in order to conserve resources.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksallocatedeviceheader">KsAllocateDeviceHeader</a>



<a href="https://docs.microsoft.com/previous-versions/ff561665(v=vs.85)">KsDefaultDispatchPnp</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kssetdevicepnpandbaseobject">KsSetDevicePnpAndBaseObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kssettargetdeviceobject">KsSetTargetDeviceObject</a>
 

 


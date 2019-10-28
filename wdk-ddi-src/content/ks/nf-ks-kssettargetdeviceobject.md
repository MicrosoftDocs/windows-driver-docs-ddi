---
UID: NF:ks.KsSetTargetDeviceObject
title: KsSetTargetDeviceObject function (ks.h)
description: The KsSetTargetDeviceObject function sets the target device object of an object. The function adds the object header to a list of object headers that have target devices.
old-location: stream\kssettargetdeviceobject.htm
tech.root: stream
ms.assetid: 0d90f70d-8cbe-4c95-ae54-494ff404631a
ms.date: 04/23/2018
ms.keywords: KsSetTargetDeviceObject, KsSetTargetDeviceObject function [Streaming Media Devices], ks/KsSetTargetDeviceObject, ksfunc_f5e0140d-a6f3-49a1-a319-f55bdd5f0734.xml, stream.kssettargetdeviceobject
ms.topic: function
f1_keywords:
 - "ks/KsSetTargetDeviceObject"
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
- KsSetTargetDeviceObject
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsSetTargetDeviceObject function


## -description


The <b>KsSetTargetDeviceObject</b> function sets the target device object of an object. The function adds the object header to a list of object headers that have target devices. 


## -parameters




### -param Header [in]

Points to a header previously allocated by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksallocateobjectheader">KsAllocateObjectHeader</a>.


### -param TargetDevice [in, optional]

Optionally contains the target device object that will be used when recalculating the stack depth for the underlying device object. If the value is <b>NULL</b>, any current setting is removed. If the value is any setting other than <b>NULL</b>, the current setting is replaced.


## -returns



None




## -remarks



The <b>KsSetTargetDeviceObject</b> function assumes that the caller has previously allocated a device header on the underlying device object with the <b>KsAllocateDeviceHeader</b> function. The presence of the device header allows future calls to the function <b>KsRecalculateStackDepth</b>, and the device header is used when the object will be forwarding IRPs through a connection to another device and needs to keep track of the stack depth.

If <b>KsSetDevicePnpAndBaseObject</b> is also used to assign the PnP object stack, that device object will also be taken into account when recalculating stack depth.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksallocatedeviceheader">KsAllocateDeviceHeader</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksallocateobjectheader">KsAllocateObjectHeader</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksrecalculatestackdepth">KsRecalculateStackDepth</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kssetdevicepnpandbaseobject">KsSetDevicePnpAndBaseObject</a>
 

 


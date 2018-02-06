---
UID: NF:ks.KsSetTargetDeviceObject
title: KsSetTargetDeviceObject function
author: windows-driver-content
description: The KsSetTargetDeviceObject function sets the target device object of an object. The function adds the object header to a list of object headers that have target devices.
old-location: stream\kssettargetdeviceobject.htm
old-project: stream
ms.assetid: 0d90f70d-8cbe-4c95-ae54-494ff404631a
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ks/KsSetTargetDeviceObject, KsSetTargetDeviceObject, ksfunc_f5e0140d-a6f3-49a1-a319-f55bdd5f0734.xml, stream.kssettargetdeviceobject, KsSetTargetDeviceObject function [Streaming Media Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ks.lib
-	Ks.dll
apiname:
-	KsSetTargetDeviceObject
product: Windows
targetos: Windows
req.typenames: 
---

# KsSetTargetDeviceObject function


## -description


The <b>KsSetTargetDeviceObject</b> function sets the target device object of an object. The function adds the object header to a list of object headers that have target devices. 


## -syntax


````
VOID KsSetTargetDeviceObject(
  _In_     KSOBJECT_HEADER Header,
  _In_opt_ PDEVICE_OBJECT  TargetDevice
);
````


## -parameters




### -param Header [in]

Points to a header previously allocated by <a href="..\ks\nf-ks-ksallocateobjectheader.md">KsAllocateObjectHeader</a>.


### -param TargetDevice [in, optional]

Optionally contains the target device object that will be used when recalculating the stack depth for the underlying device object. If the value is <b>NULL</b>, any current setting is removed. If the value is any setting other than <b>NULL</b>, the current setting is replaced.


## -returns


None



## -remarks


The <b>KsSetTargetDeviceObject</b> function assumes that the caller has previously allocated a device header on the underlying device object with the <b>KsAllocateDeviceHeader</b> function. The presence of the device header allows future calls to the function <b>KsRecalculateStackDepth</b>, and the device header is used when the object will be forwarding IRPs through a connection to another device and needs to keep track of the stack depth.

If <b>KsSetDevicePnpAndBaseObject</b> is also used to assign the PnP object stack, that device object will also be taken into account when recalculating stack depth.



## -see-also

<a href="..\ks\nf-ks-ksrecalculatestackdepth.md">KsRecalculateStackDepth</a>

<a href="..\ks\nf-ks-ksallocatedeviceheader.md">KsAllocateDeviceHeader</a>

<a href="..\ks\nf-ks-kssetdevicepnpandbaseobject.md">KsSetDevicePnpAndBaseObject</a>

<a href="..\ks\nf-ks-ksallocateobjectheader.md">KsAllocateObjectHeader</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsSetTargetDeviceObject function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


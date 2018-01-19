---
UID: NF:ks.KsSetDevicePnpAndBaseObject
title: KsSetDevicePnpAndBaseObject function
author: windows-driver-content
description: The KsSetDevicePnpAndBaseObject function sets the PnP device object in the device header, which is the next device object on the PnP stack and is the device object that PnP requests are forwarded to if KsDefaultDispatchPnp is used.
old-location: stream\kssetdevicepnpandbaseobject.htm
old-project: stream
ms.assetid: 269bbb79-c730-4b78-bf46-d502f23f039b
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KsSetDevicePnpAndBaseObject
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
req.alt-api: KsSetDevicePnpAndBaseObject
req.alt-loc: Ks.lib,Ks.dll
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
req.typenames: 
---

# KsSetDevicePnpAndBaseObject function



## -description
The <b>KsSetDevicePnpAndBaseObject</b> function sets the PnP device object in the device header, which is the next device object on the PnP stack and is the device object that PnP requests are forwarded to if <b>KsDefaultDispatchPnp</b> is used.



## -syntax

````
void KsSetDevicePnpAndBaseObject(
  _In_ KSDEVICE_HEADER Header ,
  _In_ PDEVICE_OBJECT  PnpDeviceObject ,
  _In_ PDEVICE_OBJECT  BaseDevice 
);
````


## -parameters

### -param Header  [in]

Points to a header previously allocated by <b>KsAllocateDeviceHeader</b> in which to put the PnP device object.


### -param PnpDeviceObject  [in]

Specifies the PnP device object to place in the device header, overwriting any previously set device object.


### -param BaseDevice  [in]

Specifies the base device object to which this device header is attached. This must be set if <b>KsRecalculateStackDepth</b> is used.


## -returns
None


## -remarks


## -see-also
<dl>
<dt>
<a href="..\ks\nf-ks-ksallocatedeviceheader.md">KsAllocateDeviceHeader</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksrecalculatestackdepth.md">KsRecalculateStackDepth</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsSetDevicePnpAndBaseObject function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


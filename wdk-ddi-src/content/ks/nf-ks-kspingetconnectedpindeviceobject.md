---
UID: NF:ks.KsPinGetConnectedPinDeviceObject
title: KsPinGetConnectedPinDeviceObject function
author: windows-driver-content
description: The KsPinGetConnectedPinDeviceObject function returns the device object at the top of the device stack corresponding to the sink pin attached to the source pin Pin.
old-location: stream\kspingetconnectedpindeviceobject.htm
old-project: stream
ms.assetid: 9588ef16-baf7-4e2b-a624-864ae218c385
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: avfunc_baa36f5c-d0b9-4c18-9a9d-1a128c7ba8bd.xml, stream.kspingetconnectedpindeviceobject, KsPinGetConnectedPinDeviceObject function [Streaming Media Devices], ks/KsPinGetConnectedPinDeviceObject, KsPinGetConnectedPinDeviceObject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
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
-	KsPinGetConnectedPinDeviceObject
product: Windows
targetos: Windows
req.typenames: 
---

# KsPinGetConnectedPinDeviceObject function


## -description


The<b> KsPinGetConnectedPinDeviceObject</b> function returns the device object at the top of the device stack corresponding to the sink pin attached to the source pin <i>Pin</i>.


## -syntax


````
PDEVICE_OBJECT KsPinGetConnectedPinDeviceObject(
  _In_ PKSPIN Pin
);
````


## -parameters




### -param Pin [in]

A pointer to a <a href="..\ks\ns-ks-_kspin.md">KSPIN</a> structure that is the source pin for which to obtain the connected sink pin's device object.


## -returns


If <i>Pin</i> is a source pin, <b>KsPinGetConnectedPinDeviceObject</b> returns a pointer to the <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> structure at the top of the device stack on which the sink pin resides. Otherwise, it returns <b>NULL</b>.



## -remarks


The returned device object is not necessarily the functional device object (FDO) for the device on which the sink resides, since there might exist an upper level filter driver. It is, however, the device object to which IOCTLs destined for the sink pin are sent.



## -see-also

<a href="..\ks\nf-ks-ksgetdevicefordeviceobject.md">KsGetDeviceForDeviceObject</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsPinGetConnectedPinDeviceObject function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


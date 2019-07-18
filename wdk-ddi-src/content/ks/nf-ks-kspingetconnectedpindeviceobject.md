---
UID: NF:ks.KsPinGetConnectedPinDeviceObject
title: KsPinGetConnectedPinDeviceObject function (ks.h)
description: The KsPinGetConnectedPinDeviceObject function returns the device object at the top of the device stack corresponding to the sink pin attached to the source pin Pin.
old-location: stream\kspingetconnectedpindeviceobject.htm
tech.root: stream
ms.assetid: 9588ef16-baf7-4e2b-a624-864ae218c385
ms.date: 04/23/2018
ms.keywords: KsPinGetConnectedPinDeviceObject, KsPinGetConnectedPinDeviceObject function [Streaming Media Devices], avfunc_baa36f5c-d0b9-4c18-9a9d-1a128c7ba8bd.xml, ks/KsPinGetConnectedPinDeviceObject, stream.kspingetconnectedpindeviceobject
ms.topic: function
f1_keywords:
 - "ks/KsPinGetConnectedPinDeviceObject"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ks.lib
- Ks.dll
api_name:
- KsPinGetConnectedPinDeviceObject
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsPinGetConnectedPinDeviceObject function


## -description


The<b> KsPinGetConnectedPinDeviceObject</b> function returns the device object at the top of the device stack corresponding to the sink pin attached to the source pin <i>Pin</i>.


## -parameters




### -param Pin [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_kspin">KSPIN</a> structure that is the source pin for which to obtain the connected sink pin's device object.


## -returns



If <i>Pin</i> is a source pin, <b>KsPinGetConnectedPinDeviceObject</b> returns a pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a> structure at the top of the device stack on which the sink pin resides. Otherwise, it returns <b>NULL</b>.




## -remarks



The returned device object is not necessarily the functional device object (FDO) for the device on which the sink resides, since there might exist an upper level filter driver. It is, however, the device object to which IOCTLs destined for the sink pin are sent.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksgetdevicefordeviceobject">KsGetDeviceForDeviceObject</a>
 

 


---
UID: NF:ks.KsPinGetConnectedPinDeviceObject
title: KsPinGetConnectedPinDeviceObject function (ks.h)
description: The KsPinGetConnectedPinDeviceObject function returns the device object at the top of the device stack corresponding to the sink pin attached to the source pin Pin.
old-location: stream\kspingetconnectedpindeviceobject.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KsPinGetConnectedPinDeviceObject function"]
ms.keywords: KsPinGetConnectedPinDeviceObject, KsPinGetConnectedPinDeviceObject function [Streaming Media Devices], avfunc_baa36f5c-d0b9-4c18-9a9d-1a128c7ba8bd.xml, ks/KsPinGetConnectedPinDeviceObject, stream.kspingetconnectedpindeviceobject
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
targetos: Windows
req.typenames: 
f1_keywords:
 - KsPinGetConnectedPinDeviceObject
 - ks/KsPinGetConnectedPinDeviceObject
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
---

# KsPinGetConnectedPinDeviceObject function


## -description

The<b> KsPinGetConnectedPinDeviceObject</b> function returns the device object at the top of the device stack corresponding to the sink pin attached to the source pin <i>Pin</i>.

## -parameters

### -param Pin 

[in]
A pointer to a <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_kspin">KSPIN</a> structure that is the source pin for which to obtain the connected sink pin's device object.

## -returns

If <i>Pin</i> is a source pin, <b>KsPinGetConnectedPinDeviceObject</b> returns a pointer to the <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a> structure at the top of the device stack on which the sink pin resides. Otherwise, it returns <b>NULL</b>.

## -remarks

The returned device object is not necessarily the functional device object (FDO) for the device on which the sink resides, since there might exist an upper level filter driver. It is, however, the device object to which IOCTLs destined for the sink pin are sent.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksgetdevicefordeviceobject">KsGetDeviceForDeviceObject</a>

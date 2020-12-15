---
UID: NF:ks.KsPinGetDevice
title: KsPinGetDevice function (ks.h)
description: The KsPinGetDevice function returns the AVStream device to which Pin belongs.
old-location: stream\kspingetdevice.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KsPinGetDevice function"]
ms.keywords: KsPinGetDevice, KsPinGetDevice function [Streaming Media Devices], avfunc_09495aa3-2bed-4093-a989-2ae444f1c372.xml, ks/KsPinGetDevice, stream.kspingetdevice
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - KsPinGetDevice
 - ks/KsPinGetDevice
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - KsPinGetDevice
---

# KsPinGetDevice function


## -description

The<b> KsPinGetDevice </b>function returns the AVStream device to which <i>Pin</i> belongs.

## -parameters

### -param Pin 

[in]
A pointer to a <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_kspin">KSPIN</a> structure representing the pin for which to return the owning AVStream device.

## -returns

<b>KsPinGetDevice </b>returns a pointer to a <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksdevice">KSDEVICE</a> structure representing the AVStream device to which <i>Pin</i> belongs.

## -remarks

This call is an inline function call to <a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksgetdevice">KsGetDevice</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksdevice">KSDEVICE</a>



<a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksdevice_descriptor">KSDEVICE_DESCRIPTOR</a>



<a href="/windows-hardware/drivers/ddi/ks/ns-ks-_kspin">KSPIN</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksgetdevice">KsGetDevice</a>

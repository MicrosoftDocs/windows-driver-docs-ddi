---
UID: NF:ks.KsFilterFactoryGetDevice
title: KsFilterFactoryGetDevice function (ks.h)
description: The KsFilterFactoryGetDevice function returns the AVStream device to which FilterFactory belongs.
old-location: stream\ksfilterfactorygetdevice.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KsFilterFactoryGetDevice function"]
ms.keywords: KsFilterFactoryGetDevice, KsFilterFactoryGetDevice function [Streaming Media Devices], avfunc_1e2ec536-69a1-4606-9d99-ebdebd25c89a.xml, ks/KsFilterFactoryGetDevice, stream.ksfilterfactorygetdevice
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
 - KsFilterFactoryGetDevice
 - ks/KsFilterFactoryGetDevice
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - KsFilterFactoryGetDevice
---

# KsFilterFactoryGetDevice function


## -description

The<b> KsFilterFactoryGetDevice </b>function returns the AVStream device to which <i>FilterFactory </i>belongs.

## -parameters

### -param FilterFactory [in]


A pointer to a <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilterfactory">KSFILTERFACTORY</a> structure for which to find the corresponding AVStream device.

## -returns

Returns a pointer to a <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksdevice">KSDEVICE</a> structure representing the AVStream device to which <i>FilterFactory</i> belongs.

## -remarks

This call is an inline function call to <a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksgetdevice">KsGetDevice</a>.

For more information about the AVStream object hierarchy, see  <a href="/windows-hardware/drivers/stream/avstream-overview">AVStream Overview</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksdevice">KSDEVICE</a>



<a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilterfactory">KSFILTERFACTORY</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksgetdevice">KsGetDevice</a>

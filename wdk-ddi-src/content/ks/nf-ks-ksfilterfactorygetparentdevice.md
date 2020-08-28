---
UID: NF:ks.KsFilterFactoryGetParentDevice
title: KsFilterFactoryGetParentDevice function (ks.h)
description: The KsFilterFactoryGetParentDevice function returns the parent device of the given filter factory.
old-location: stream\ksfilterfactorygetparentdevice.htm
tech.root: stream
ms.assetid: ac1d10dc-d3cb-4a83-9f52-34ea90d2193b
ms.date: 04/23/2018
keywords: ["KsFilterFactoryGetParentDevice function"]
ms.keywords: KsFilterFactoryGetParentDevice, KsFilterFactoryGetParentDevice function [Streaming Media Devices], avfunc_35d9d582-f7d6-4c1f-8998-a6664527db2c.xml, ks/KsFilterFactoryGetParentDevice, stream.ksfilterfactorygetparentdevice
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
 - KsFilterFactoryGetParentDevice
 - ks/KsFilterFactoryGetParentDevice
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - KsFilterFactoryGetParentDevice
---

# KsFilterFactoryGetParentDevice function


## -description

The<b> KsFilterFactoryGetParentDevice</b> function returns the parent device of the given filter factory.

## -parameters

### -param FilterFactory 

[in]
A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilterfactory">KSFILTERFACTORY</a> structure for which to return the parent device.

## -returns

<b>KsFilterFactoryGetParentDevice</b> returns a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksdevice">KSDEVICE</a> structure representing the parent device of the filter factory. This is the AVStream device to which the filter factory belongs.

## -remarks

This call is an inline function call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksgetparent">KsGetParent</a>. Note that the object hierarchy is guaranteed to be stable only while the appropriate mutex is held, in this case the device mutex. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/mutexes-in-avstream">Mutexes in AVStream</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksdevice">KSDEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilterfactory">KSFILTERFACTORY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksgetparent">KsGetParent</a>


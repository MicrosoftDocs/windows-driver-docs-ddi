---
UID: NF:ks.KsDeviceGetFirstChildFilterFactory
title: KsDeviceGetFirstChildFilterFactory function (ks.h)
description: The KsDeviceGetFirstChildFilterFactory function returns the first child filter factory belonging to a given AVStream device.
old-location: stream\ksdevicegetfirstchildfilterfactory.htm
tech.root: stream
ms.assetid: af388fd1-c95b-42ae-9d18-5fb416c28bc1
ms.date: 04/23/2018
keywords: ["KsDeviceGetFirstChildFilterFactory function"]
ms.keywords: KsDeviceGetFirstChildFilterFactory, KsDeviceGetFirstChildFilterFactory function [Streaming Media Devices], avfunc_99fdc67f-eca0-460d-b1fb-d9881bd6e4c9.xml, ks/KsDeviceGetFirstChildFilterFactory, stream.ksdevicegetfirstchildfilterfactory
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
 - KsDeviceGetFirstChildFilterFactory
 - ks/KsDeviceGetFirstChildFilterFactory
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - KsDeviceGetFirstChildFilterFactory
---

# KsDeviceGetFirstChildFilterFactory function


## -description

The<b> KsDeviceGetFirstChildFilterFactory</b> function returns the first child filter factory belonging to a given AVStream device.

## -parameters

### -param Device 

[in]
A pointer to a <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksdevice">KSDEVICE</a> structure representing the AVStream device for which to find the first child filter factory.

## -returns

Returns a pointer to a <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilterfactory">KSFILTERFACTORY</a> structure representing the first child filter factory of <i>Device</i>. If there are no filter factories registered on <i>Device</i>, <b>NULL</b> is returned.

## -remarks

This call is an inline function call to <a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksgetfirstchild">KsGetFirstChild</a>. Note that the object hierarchy is only guaranteed stable while the appropriate mutex is held, in this case the device mutex. For more information, see <a href="/windows-hardware/drivers/stream/mutexes-in-avstream">Mutexes in AVStream</a>.

For a graphical representation of AVStream parent/child relationships, see the diagram in <a href="/windows-hardware/drivers/stream/avstream-object-hierarchy">AVStream Object Hierarchy</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksdevice">KSDEVICE</a>



<a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilterfactory">KSFILTERFACTORY</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksfilterfactorygetnextsiblingfilterfactory">KsFilterFactoryGetNextSiblingFilterFactory</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksgetfirstchild">KsGetFirstChild</a>
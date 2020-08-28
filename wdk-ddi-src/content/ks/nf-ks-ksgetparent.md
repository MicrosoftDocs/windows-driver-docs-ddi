---
UID: NF:ks.KsGetParent
title: KsGetParent function (ks.h)
description: The KsGetParent function acquires the parent of the given object.
old-location: stream\ksgetparent.htm
tech.root: stream
ms.assetid: d7804745-295f-491a-80f4-84441598bbf4
ms.date: 04/23/2018
keywords: ["KsGetParent function"]
ms.keywords: KsGetParent, KsGetParent function [Streaming Media Devices], avfunc_da3c1932-98b1-4f29-8b5a-4663077759e9.xml, ks/KsGetParent, stream.ksgetparent
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - KsGetParent
 - ks/KsGetParent
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsGetParent
---

# KsGetParent function


## -description

The<b> KsGetParent</b> function acquires the parent of the given object.

## -parameters

### -param Object 

[in]
A pointer to the AVStream object for which to find the parent. Must be a pointer to one of the following types: <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksdevice">KSDEVICE</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilterfactory">KSFILTERFACTORY</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter">KSFILTER</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_kspin">KSPIN</a>. Callers must manually typecast the object to a PVOID.

## -returns

<b>KsGetParent</b> returns the parent of <i>Object</i> as a PVOID. Callers must manually cast this return value to whatever the type of the parent of <i>Object</i> is.

## -remarks

For a graphical representation of AVStream parent/child relationships, see the diagram in <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avstream-object-hierarchy">AVStream Object Hierarchy</a>.

The object hierarchy is only guaranteed stable while the appropriate mutex is held, in this case the device mutex. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/mutexes-in-avstream">Mutexes in AVStream</a>.

Minidrivers rarely use this function directly. Callers of <b>KsGetParent</b> must manually perform typecasts to and from PVOID. There are a number of inline versions that do the casting for you: <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksfilterfactorygetparentdevice">KsFilterFactoryGetParentDevice</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksfiltergetparentfilterfactory">KsFilterGetParentFilterFactory</a>, and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kspingetparentfilter">KsPinGetParentFilter</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksdevice">KSDEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter">KSFILTER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilterfactory">KSFILTERFACTORY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_kspin">KSPIN</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksfilterfactorygetparentdevice">KsFilterFactoryGetParentDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksfiltergetparentfilterfactory">KsFilterGetParentFilterFactory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kspingetparentfilter">KsPinGetParentFilter</a>


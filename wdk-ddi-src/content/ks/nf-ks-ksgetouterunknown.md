---
UID: NF:ks.KsGetOuterUnknown
title: KsGetOuterUnknown function (ks.h)
description: The KsGetOuterUnknown function returns the outer IUnknown of a given AVStream object.
old-location: stream\ksgetouterunknown.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KsGetOuterUnknown function"]
ms.keywords: KsGetOuterUnknown, KsGetOuterUnknown function [Streaming Media Devices], avfunc_5b660e76-03af-4fba-92f9-f11eeeaa3da0.xml, ks/KsGetOuterUnknown, stream.ksgetouterunknown
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
 - KsGetOuterUnknown
 - ks/KsGetOuterUnknown
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsGetOuterUnknown
---

# KsGetOuterUnknown function


## -description

The<b> KsGetOuterUnknown </b>function returns the outer <b>IUnknown</b> of a given AVStream object.

## -parameters

### -param Object [in]


A pointer to an AVStream object for which to return the outer <b>IUnknown</b> interface.

## -returns

<b>KsGetOuterUnknown</b> returns a pointer to the outer <b>IUnknown</b> interface of <i>Object</i>. The client can then call the <b>QueryInterface</b> method to determine whether the component supports a given interface.

## -remarks

Minidrivers should not call this function directly. Instead, use one of the inline versions that perform automatic typecasting: <a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksdevicegetouterunknown">KsDeviceGetOuterUnknown</a>, <a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksfilterfactorygetouterunknown">KsFilterFactoryGetOuterUnknown</a>, <a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksfiltergetouterunknown">KsFilterGetOuterUnknown</a>, <a href="/windows-hardware/drivers/ddi/ks/nf-ks-kspingetouterunknown">KsPinGetOuterUnknown</a>.

Minidrivers using this function must include <i>kcom.h</i> and use a C++ compiler.

## -see-also

<a href="/windows-hardware/drivers/ddi/ksproxy/nn-ksproxy-ikscontrol">IKsControl</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksdevicegetouterunknown">KsDeviceGetOuterUnknown</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksfilterfactorygetouterunknown">KsFilterFactoryGetOuterUnknown</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksfiltergetouterunknown">KsFilterGetOuterUnknown</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-kspingetouterunknown">KsPinGetOuterUnknown</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksregisteraggregatedclientunknown">KsRegisterAggregatedClientUnknown</a>

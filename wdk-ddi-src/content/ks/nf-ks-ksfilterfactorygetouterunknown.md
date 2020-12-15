---
UID: NF:ks.KsFilterFactoryGetOuterUnknown
title: KsFilterFactoryGetOuterUnknown function (ks.h)
description: The KsFilterFactoryGetOuterUnknown function returns the outer IUnknown of the specified filter factory.
old-location: stream\ksfilterfactorygetouterunknown.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KsFilterFactoryGetOuterUnknown function"]
ms.keywords: KsFilterFactoryGetOuterUnknown, KsFilterFactoryGetOuterUnknown function [Streaming Media Devices], avfunc_4a154d39-a344-4f58-8abe-cbf2a0926271.xml, ks/KsFilterFactoryGetOuterUnknown, stream.ksfilterfactorygetouterunknown
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
 - KsFilterFactoryGetOuterUnknown
 - ks/KsFilterFactoryGetOuterUnknown
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - KsFilterFactoryGetOuterUnknown
---

# KsFilterFactoryGetOuterUnknown function


## -description

The<b> KsFilterFactoryGetOuterUnknown </b>function returns the outer <b>IUnknown</b> of the specified filter factory.

## -parameters

### -param FilterFactory 

[in]
A pointer to a <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilterfactory">KSFILTERFACTORY</a> for which to return the outer unknown interface.

## -returns

<b>KsFilterFactoryGetOuterUnknown </b>returns the outer <b>IUnknown</b> of <i>FilterFactory</i>. The minidriver can then use it to query for other interfaces.

## -remarks

This call is an inline function call to <a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksgetouterunknown">KsGetOuterUnknown</a>.

For more information, see <a href="/windows-hardware/drivers/stream/avstream-overview">AVStream Overview</a>

## -see-also

<a href="/windows-hardware/drivers/ddi/ksproxy/nn-ksproxy-ikscontrol">IKsControl</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksfiltergetouterunknown">KsFilterGetOuterUnknown</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksfilterregisteraggregatedclientunknown">KsFilterRegisterAggregatedClientUnknown</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksgetouterunknown">KsGetOuterUnknown</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-kspingetouterunknown">KsPinGetOuterUnknown</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksregisteraggregatedclientunknown">KsRegisterAggregatedClientUnknown</a>

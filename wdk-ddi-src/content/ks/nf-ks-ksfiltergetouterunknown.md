---
UID: NF:ks.KsFilterGetOuterUnknown
title: KsFilterGetOuterUnknown function (ks.h)
description: The KsFilterGetOuterUnknown function returns the outer IUnknown interface of the filter specified by Filter.
old-location: stream\ksfiltergetouterunknown.htm
tech.root: stream
ms.assetid: 599a6583-dcf2-4fe3-949a-5072bff9915c
ms.date: 04/23/2018
keywords: ["KsFilterGetOuterUnknown function"]
ms.keywords: KsFilterGetOuterUnknown, KsFilterGetOuterUnknown function [Streaming Media Devices], avfunc_32947579-50ca-4942-a594-b991c42d6681.xml, ks/KsFilterGetOuterUnknown, stream.ksfiltergetouterunknown
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
 - KsFilterGetOuterUnknown
 - ks/KsFilterGetOuterUnknown
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - KsFilterGetOuterUnknown
---

# KsFilterGetOuterUnknown function


## -description

The<b> KsFilterGetOuterUnknown </b>function returns the outer <b>IUnknown</b> interface of the filter specified by <i>Filter</i>.

## -parameters

### -param Filter 

[in]
A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter">KSFILTER</a> structure for which to return the outer <b>IUnknown</b>.

## -returns

<b>KsFilterGetOuterUnknown </b>returns a pointer to the outer <b>IUknown</b> interface of <i>Filter</i>. The interface can then be used to query for other interfaces, or it can be used in conjunction with a <b>Ks</b><i>Xxx</i><b>RegisterAggregatedClientUnknown</b> call to cause <i>Filter</i> to aggregate a minidriver supplied COM object.

## -remarks

This call is an inline function call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksgetouterunknown">KsGetOuterUnknown</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avstream-overview">AVStream Overview</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nn-ksproxy-ikscontrol">IKsControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksfilterregisteraggregatedclientunknown">KsFilterRegisterAggregatedClientUnknown</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksgetouterunknown">KsGetOuterUnknown</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kspingetouterunknown">KsPinGetOuterUnknown</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kspinregisteraggregatedclientunknown">KsPinRegisterAggregatedClientUnknown</a>



<b>KsRegisterAggregatedClientUnknown</b>


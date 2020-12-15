---
UID: NF:ks.KsFilterRegisterAggregatedClientUnknown
title: KsFilterRegisterAggregatedClientUnknown function (ks.h)
description: This inline function is a wrapper for KsRegisterAggregatedClientUnknown.
old-location: stream\ksfilterregisteraggregatedclientunknown.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KsFilterRegisterAggregatedClientUnknown function"]
ms.keywords: KsFilterRegisterAggregatedClientUnknown, KsFilterRegisterAggregatedClientUnknown function [Streaming Media Devices], avfunc_c485334a-83bd-474e-abfc-ced331ca55db.xml, ks/KsFilterRegisterAggregatedClientUnknown, stream.ksfilterregisteraggregatedclientunknown
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
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - KsFilterRegisterAggregatedClientUnknown
 - ks/KsFilterRegisterAggregatedClientUnknown
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - KsFilterRegisterAggregatedClientUnknown
---

# KsFilterRegisterAggregatedClientUnknown function


## -description

This inline function is a wrapper for <a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksregisteraggregatedclientunknown">KsRegisterAggregatedClientUnknown</a>.

## -parameters

### -param Filter 

[in]
A pointer to the specified AVStream <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter">KSFILTER</a> structure.

### -param ClientUnknown 

[in]
The client <b>IUnknown</b> interface object.

## -returns

<b>KsFilterRegisterAggregatedClientUnknown</b> returns a pointer to an <b>IUnknown</b> interface representing the newly created aggregate object.

## -remarks

Note that this inline function only performs a typecast and then calls <a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksregisteraggregatedclientunknown">KsRegisterAggregatedClientUnknown</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksregisteraggregatedclientunknown">KsRegisterAggregatedClientUnknown</a>

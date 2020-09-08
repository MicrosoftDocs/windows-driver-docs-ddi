---
UID: NF:ks.KsFilterFactoryUpdateCacheData
title: KsFilterFactoryUpdateCacheData function (ks.h)
description: The KsFilterFactoryUpdateCacheData function updates the FilterData registry key and the Medium cache (a set of registry keys) for a given filter factory.
old-location: stream\ksfilterfactoryupdatecachedata.htm
tech.root: stream
ms.assetid: a5c868a5-0e79-482b-9694-02cae2de99ca
ms.date: 04/23/2018
keywords: ["KsFilterFactoryUpdateCacheData function"]
ms.keywords: KsFilterFactoryUpdateCacheData, KsFilterFactoryUpdateCacheData function [Streaming Media Devices], avfunc_2fdbd12c-b074-415e-8de3-bfbe61ef198a.xml, ks/KsFilterFactoryUpdateCacheData, stream.ksfilterfactoryupdatecachedata
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 9.0 and later DirectX versions.
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
 - KsFilterFactoryUpdateCacheData
 - ks/KsFilterFactoryUpdateCacheData
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsFilterFactoryUpdateCacheData
---

# KsFilterFactoryUpdateCacheData function


## -description

The <b>KsFilterFactoryUpdateCacheData</b> function updates the FilterData registry key and the Medium cache (a set of registry keys) for a given filter factory.

## -parameters

### -param FilterFactory 

[in]
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilterfactory">KSFILTERFACTORY</a> for which to update FilterData and Medium cache in the registry.

### -param FilterDescriptor 

[in, optional]
An optional <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter_descriptor">KSFILTER_DESCRIPTOR</a> for which the FilterData key and Medium cache will be updated. If <b>NULL</b>, <i>FilterFactory</i>'s descriptor is used instead. Provide if the filter factory uses dynamic pins and needs to update information for pins that have not yet been instantiated.

## -returns

<b>
             KsFilterFactoryUpdateCacheData</b> returns STATUS_SUCCESS or a failure code, indicating whether the relevant registry information was successfully updated. It returns STATUS_INVALID_PARAMETER if no device interface is found that corresponds to the categories passed in the filter descriptor.

## -remarks

This function updates the FilterData key and Medium cache for all categories specified in <i>FilterDescriptor</i>. If <i>FilterDescriptor</i> is <b>NULL</b>, the FilterData and Medium cache are updated for all categories specified in <i>FilterFactory</i>'s <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter_descriptor">KSFILTER_DESCRIPTOR</a> member.


<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksregisterfilterwithnokspins">KsRegisterFilterWithNoKSPins</a> provides similar functionality, but should not be used if two instances of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter_descriptor">KSFILTER_DESCRIPTOR</a> under the same <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksdevice">KSDEVICE</a> are registered in the same category, and differ only in reference GUID. In this case, <b>KsRegisterFilterWithNoKSPins</b> updates data only for the first, even though the second may have been specified.

Do not use this routine in place of <b>KsRegisterFilterWithNoKSPins</b> for filters with no KS pins, such as analog style crossbars. Use this routine only for a specific filter for which the minidriver is passing the corresponding filter factory.

In addition, <b>KsRegisterFilterWithNoKSPins</b> only allows one medium per registered pin. This may not be sufficient for a BDA minidriver.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avstream-object-hierarchy">AVStream Object Hierarchy</a>.

<div class="alert"><b>Note</b>  The <b>KsFilterFactoryUpdateCacheData</b> function can only be called in PASSIVE_LEVEL.</div>
<div> </div>

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilterfactory">KSFILTERFACTORY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter_descriptor">KSFILTER_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksregisterfilterwithnokspins">KsRegisterFilterWithNoKSPins</a>


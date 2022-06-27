---
UID: NF:bdasup.BdaFilterFactoryUpdateCacheData
title: BdaFilterFactoryUpdateCacheData function (bdasup.h)
description: The BdaFilterFactoryUpdateCacheData function updates the pin data cache for an instance of a filter.
tech.root: stream
ms.date: 04/25/2022
keywords: ["BdaFilterFactoryUpdateCacheData function"]
ms.keywords: BdaFilterFactoryUpdateCacheData, BdaFilterFactoryUpdateCacheData function [Streaming Media Devices], bdaref_b384500e-7b80-4413-a950-f7cf7aed3f54.xml, bdasup/BdaFilterFactoryUpdateCacheData, stream.bdafilterfactoryupdatecachedata
req.header: bdasup.h
req.include-header: Bdasup.h
req.target-type: Desktop
req.target-min-winverclnt:
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
req.lib: Bdasup.lib
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - BdaFilterFactoryUpdateCacheData
 - bdasup/BdaFilterFactoryUpdateCacheData
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Bdasup.lib
 - Bdasup.dll
api_name:
 - BdaFilterFactoryUpdateCacheData
---

## -description

The **BdaFilterFactoryUpdateCacheData** function updates the pin data cache for an instance of a filter.

## -parameters

### -param pFilterFactory [in]

Points to the [KSFILTERFACTORY](/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilterfactory) for which to update the pin data cache.

### -param pFilterDescriptor [in, optional]

Points to an optional [KSFILTER_DESCRIPTOR](/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter_descriptor) for which the pin data cache will be updated. If **NULL**, *pFilterFactory*'s descriptor is used instead. This parameter enables dynamic pin creation, that is, pin creation that occurs after a filter's create dispatch routine completes.

## -returns

Returns STATUS_SUCCESS or an appropriate error code. Returns STATUS_INVALID_PARAMETER if no device interface is found that corresponds to the categories passed in the filter descriptor.

## -remarks

A BDA minidriver calls the **BdaFilterFactoryUpdateCacheData** function to update the pin data cache for all pins specified at *pFilterDescriptor*. In this call, the BDA minidriver typically passes the **pFilterDescriptor** member of a [BDA_FILTER_TEMPLATE](/windows-hardware/drivers/ddi/bdasup/ns-bdasup-_bda_filter_template) structure that describes the template topology for the BDA filter to *pFilterDescriptor*. If *pFilterDescriptor* is **NULL**, the cached information will be updated for all pin factories specified at *pFilterFactory*'s KSFILTER_DESCRIPTOR member. For information about the pin data cache, see [Caching Pin Information for DirectShow](/windows-hardware/drivers/stream/caching-pin-information-for-directshow).

The [KsRegisterFilterWithNoKSPins](/windows-hardware/drivers/ddi/ks/nf-ks-ksregisterfilterwithnokspins) function provides similar functionality but only allows one medium per registered pin. This may not be sufficient for a BDA minidriver.

## -see-also

[BDA_FILTER_TEMPLATE](/windows-hardware/drivers/ddi/bdasup/ns-bdasup-_bda_filter_template)

[KSFILTERFACTORY](/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilterfactory)

[KSFILTER_DESCRIPTOR](/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter_descriptor)

[KsRegisterFilterWithNoKSPins](/windows-hardware/drivers/ddi/ks/nf-ks-ksregisterfilterwithnokspins)

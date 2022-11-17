---
UID: NF:ks.KsFilterFactoryUpdateCacheData
title: KsFilterFactoryUpdateCacheData function (ks.h)
description: The KsFilterFactoryUpdateCacheData function updates the FilterData registry key and the Medium cache (a set of registry keys) for a given filter factory.
tech.root: stream
ms.date: 11/16/2022
keywords: ["KsFilterFactoryUpdateCacheData function"]
ms.keywords: KsFilterFactoryUpdateCacheData, KsFilterFactoryUpdateCacheData function [Streaming Media Devices], avfunc_2fdbd12c-b074-415e-8de3-bfbe61ef198a.xml, ks/KsFilterFactoryUpdateCacheData, stream.ksfilterfactoryupdatecachedata
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
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

## -description

The KsFilterFactoryUpdateCacheData function updates the FilterData registry key and the Medium cache (a set of registry keys) for a given filter factory.

## -parameters

### -param FilterFactory [in]

The [**KSFILTERFACTORY**](/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilterfactory) for which to update FilterData and Medium cache in the registry.

### -param FilterDescriptor [in, optional]

An optional [**KSFILTER_DESCRIPTOR**](/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter_descriptor) for which the FilterData key and Medium cache will be updated. If **NULL**, *FilterFactory*'s descriptor is used instead. Provide if the filter factory uses dynamic pins and needs to update information for pins that have not yet been instantiated.

## -returns

**KsFilterFactoryUpdateCacheData** returns STATUS_SUCCESS or a failure code, indicating whether the relevant registry information was successfully updated. It returns STATUS_INVALID_PARAMETER if no device interface is found that corresponds to the categories passed in the filter descriptor.

## -remarks

This function updates the FilterData key and Medium cache for all categories specified in *FilterDescriptor*. If *FilterDescriptor* is **NULL**, the FilterData and Medium cache are updated for all categories specified in *FilterFactory*'s [**KSFILTER_DESCRIPTOR**](/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter_descriptor) member.

[KsRegisterFilterWithNoKSPins](/windows-hardware/drivers/ddi/ks/nf-ks-ksregisterfilterwithnokspins) provides similar functionality, but should not be used if two instances of [**KSFILTER_DESCRIPTOR**](/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter_descriptor) under the same [**KSDEVICE**](/windows-hardware/drivers/ddi/ks/ns-ks-_ksdevice) are registered in the same category, and differ only in reference GUID. In this case, **KsRegisterFilterWithNoKSPins** updates data only for the first, even though the second may have been specified.

Do not use this routine in place of **KsRegisterFilterWithNoKSPins** for filters with no KS pins, such as analog style crossbars. Use this routine only for a specific filter for which the minidriver is passing the corresponding filter factory.

In addition, **KsRegisterFilterWithNoKSPins** only allows one medium per registered pin. This may not be sufficient for a BDA minidriver.

For more information, see [AVStream Object Hierarchy](/windows-hardware/drivers/stream/avstream-object-hierarchy).

> [!NOTE]
> The KsFilterFactoryUpdateCacheData function can only be called in PASSIVE_LEVEL.

## -see-also

[**KSFILTERFACTORY**](/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilterfactory)

[**KSFILTER_DESCRIPTOR**](/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter_descriptor)

[KsRegisterFilterWithNoKSPins](/windows-hardware/drivers/ddi/ks/nf-ks-ksregisterfilterwithnokspins)

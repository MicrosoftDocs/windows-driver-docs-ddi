---
UID: NF:bdasup.BdaFilterFactoryUpdateCacheData
title: BdaFilterFactoryUpdateCacheData function (bdasup.h)
description: The BdaFilterFactoryUpdateCacheData function updates the pin data cache for an instance of a filter.
old-location: stream\bdafilterfactoryupdatecachedata.htm
tech.root: stream
ms.assetid: c4b8220a-bd54-4e41-a00e-3750a3f03cae
ms.date: 04/23/2018
keywords: ["BdaFilterFactoryUpdateCacheData function"]
ms.keywords: BdaFilterFactoryUpdateCacheData, BdaFilterFactoryUpdateCacheData function [Streaming Media Devices], bdaref_b384500e-7b80-4413-a950-f7cf7aed3f54.xml, bdasup/BdaFilterFactoryUpdateCacheData, stream.bdafilterfactoryupdatecachedata
f1_keywords:
 - "bdasup/BdaFilterFactoryUpdateCacheData"
req.header: bdasup.h
req.include-header: Bdasup.h
req.target-type: Desktop
req.target-min-winverclnt: Available on Microsoft Windows XP and later operating systems. This routine is available on the Windows 2000 platform only if Microsoft DirectX 9.0 and later is installed on that platform.
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
product:
- Windows
targetos: Windows
req.typenames: 
---

# BdaFilterFactoryUpdateCacheData function


## -description


The<b> BdaFilterFactoryUpdateCacheData</b> function updates the pin data cache for an instance of a filter.


## -parameters




### -param pFilterFactory [in]

Points to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilterfactory">KSFILTERFACTORY</a> for which to update the pin data cache.


### -param OPTIONAL






#### - pFilterDescriptor [in, optional]

Points to an optional <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter_descriptor">KSFILTER_DESCRIPTOR</a> for which the pin data cache will be updated. If <b>NULL</b>, <i>pFilterFactory</i>'s descriptor is used instead. This parameter enables dynamic pin creation, that is, pin creation that occurs after a filter's create dispatch routine completes.


## -returns



Returns STATUS_SUCCESS or an appropriate error code. Returns STATUS_INVALID_PARAMETER if no device interface is found that corresponds to the categories passed in the filter descriptor.




## -remarks



A BDA minidriver calls the <b>BdaFilterFactoryUpdateCacheData</b> function to update the pin data cache for all pins specified at <i>pFilterDescriptor</i>. In this call, the BDA minidriver typically passes the <b>pFilterDescriptor</b> member of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bdasup/ns-bdasup-_bda_filter_template">BDA_FILTER_TEMPLATE</a> structure that describes the template topology for the BDA filter to <i>pFilterDescriptor</i>. If <i>pFilterDescriptor</i> is <b>NULL</b>, the cached information will be updated for all pin factories specified at <i>pFilterFactory</i>'s KSFILTER_DESCRIPTOR member. For information about the pin data cache, see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/caching-pin-information-for-directshow">Caching Pin Information for DirectShow</a>. 

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksregisterfilterwithnokspins">KsRegisterFilterWithNoKSPins</a> function provides similar functionality but only allows one medium per registered pin. This may not be sufficient for a BDA minidriver.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bdasup/ns-bdasup-_bda_filter_template">BDA_FILTER_TEMPLATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilterfactory">KSFILTERFACTORY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter_descriptor">KSFILTER_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksregisterfilterwithnokspins">KsRegisterFilterWithNoKSPins</a>
 

 


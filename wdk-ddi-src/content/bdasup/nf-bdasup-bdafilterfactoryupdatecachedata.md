---
UID: NF:bdasup.BdaFilterFactoryUpdateCacheData
title: BdaFilterFactoryUpdateCacheData function
author: windows-driver-content
description: The BdaFilterFactoryUpdateCacheData function updates the pin data cache for an instance of a filter.
old-location: stream\bdafilterfactoryupdatecachedata.htm
old-project: stream
ms.assetid: c4b8220a-bd54-4e41-a00e-3750a3f03cae
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: BdaFilterFactoryUpdateCacheData, BdaFilterFactoryUpdateCacheData function [Streaming Media Devices], bdaref_b384500e-7b80-4413-a950-f7cf7aed3f54.xml, bdasup/BdaFilterFactoryUpdateCacheData, stream.bdafilterfactoryupdatecachedata
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Bdasup.lib
-	Bdasup.dll
api_name:
-	BdaFilterFactoryUpdateCacheData
product: Windows
targetos: Windows
req.typenames: 
---

# BdaFilterFactoryUpdateCacheData function


## -description


The<b> BdaFilterFactoryUpdateCacheData</b> function updates the pin data cache for an instance of a filter.


## -parameters




### -param pFilterFactory [in]

Points to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562530">KSFILTERFACTORY</a> for which to update the pin data cache.


### -param OPTIONAL

TBD




#### - pFilterDescriptor [in, optional]

Points to an optional <a href="https://msdn.microsoft.com/library/windows/hardware/ff562553">KSFILTER_DESCRIPTOR</a> for which the pin data cache will be updated. If <b>NULL</b>, <i>pFilterFactory</i>'s descriptor is used instead. This parameter enables dynamic pin creation, that is, pin creation that occurs after a filter's create dispatch routine completes.


## -returns



Returns STATUS_SUCCESS or an appropriate error code. Returns STATUS_INVALID_PARAMETER if no device interface is found that corresponds to the categories passed in the filter descriptor.




## -remarks



A BDA minidriver calls the <b>BdaFilterFactoryUpdateCacheData</b> function to update the pin data cache for all pins specified at <i>pFilterDescriptor</i>. In this call, the BDA minidriver typically passes the <b>pFilterDescriptor</b> member of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff556523">BDA_FILTER_TEMPLATE</a> structure that describes the template topology for the BDA filter to <i>pFilterDescriptor</i>. If <i>pFilterDescriptor</i> is <b>NULL</b>, the cached information will be updated for all pin factories specified at <i>pFilterFactory</i>'s KSFILTER_DESCRIPTOR member. For information about the pin data cache, see <a href="https://msdn.microsoft.com/1e6a973b-32d2-4ac2-9cd6-f4d3c329cecf">Caching Pin Information for DirectShow</a>. 

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff566773">KsRegisterFilterWithNoKSPins</a> function provides similar functionality but only allows one medium per registered pin. This may not be sufficient for a BDA minidriver.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556523">BDA_FILTER_TEMPLATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562530">KSFILTERFACTORY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562553">KSFILTER_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566773">KsRegisterFilterWithNoKSPins</a>
 

 


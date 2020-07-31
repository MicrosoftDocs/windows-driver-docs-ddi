---
UID: NF:ksproxy.KsGetMultiplePinFactoryItems
title: KsGetMultiplePinFactoryItems function (ksproxy.h)
description: The KsGetMultiplePinFactoryItems function retrieves pin property items in a variable length data buffer.
old-location: stream\ksgetmultiplepinfactoryitems.htm
tech.root: stream
ms.assetid: 43210484-dcae-49b7-bda3-50d6c06ee2c0
ms.date: 04/23/2018
keywords: ["KsGetMultiplePinFactoryItems function"]
ms.keywords: KsGetMultiplePinFactoryItems, KsGetMultiplePinFactoryItems function [Streaming Media Devices], ksproxy/KsGetMultiplePinFactoryItems, ksproxy_cd252212-9317-4e1a-9f57-ee18afc23766.xml, stream.ksgetmultiplepinfactoryitems
f1_keywords:
 - "ksproxy/KsGetMultiplePinFactoryItems"
 - "KsGetMultiplePinFactoryItems"
req.header: ksproxy.h
req.include-header: Ksproxy.h
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
req.lib: Ksproxy.lib
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ksproxy.lib
- Ksproxy.dll
api_name:
- KsGetMultiplePinFactoryItems
targetos: Windows
req.typenames: 
---

# KsGetMultiplePinFactoryItems function


## -description


The <b>KsGetMultiplePinFactoryItems</b> function retrieves pin property items in a variable length data buffer. 


## -parameters




### -param FilterHandle [in]

Handle to the filter that contains the pin factory to query.


### -param PinFactoryId [in]

Identifier of the pin factory against which the property items are being returned.


### -param PropertyId [in]

Identifier of the property in the pin property set (<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/kspropsetid-pin">KSPROPSETID_Pin</a>) to query.


### -param Items [out]

Pointer to a buffer to receive the property items. If successfully retrieved, this pointer must be subsequently deleted with the <b>CoTaskMemFree</b> function.


## -returns



Returns NOERROR if successful; otherwise, returns an error code.




## -remarks



The <b>KsGetMultiplePinFactoryItems</b> function queries for the data size, in bytes, of the requested property, allocates a buffer, and retrieves the data.

For more information about <b>CoTaskMemFree</b>, see the Microsoft Windows SDK documentation.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nn-ksproxy-ikspinfactory">IKsPinFactory</a>



<a href="https://docs.microsoft.com/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/kspropsetid-pin">KSPROPSETID_Pin</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksp_pin">KSP_PIN</a>
 

 


---
UID: NF:ks.KsFilterCreatePinFactory
title: KsFilterCreatePinFactory function (ks.h)
description: The KsFilterCreatePinFactory function creates a new pin factory on the specified filter.
old-location: stream\ksfiltercreatepinfactory.htm
tech.root: stream
ms.assetid: f4c8de23-dc92-41b0-82ee-2622d3942c0e
ms.date: 04/23/2018
keywords: ["KsFilterCreatePinFactory function"]
ms.keywords: KsFilterCreatePinFactory, KsFilterCreatePinFactory function [Streaming Media Devices], avfunc_845b66c4-755e-43db-afdc-db929b6bd1c6.xml, ks/KsFilterCreatePinFactory, stream.ksfiltercreatepinfactory
f1_keywords:
 - "ks/KsFilterCreatePinFactory"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ks.lib
- Ks.dll
api_name:
- KsFilterCreatePinFactory
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsFilterCreatePinFactory function


## -description


The<b> KsFilterCreatePinFactory</b> function creates a new pin factory on the specified filter.


## -parameters




### -param Filter [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter">KSFILTER</a> structure for which to create a new pin factory.


### -param PinDescriptor [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_kspin_descriptor_ex">KSPIN_DESCRIPTOR_EX</a> structure that describes the pins this factory will create.


### -param PinID [out]

A pointer to the location containing the ID of the new factory.


## -returns



<b>KsFilterCreatePinFactory</b> returns the success or failure of the attempt to create the pin factory. Failure may occur due to invalid parameters or low memory.




## -remarks



Note that the filter control mutex must be held before calling this function. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/mutexes-in-avstream">Mutexes in AVStream</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksfiltercreatenode">KsFilterCreateNode</a>
 

 


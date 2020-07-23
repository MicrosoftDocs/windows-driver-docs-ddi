---
UID: NF:ks.KsFilterGetChildPinCount
title: KsFilterGetChildPinCount function (ks.h)
description: The KsFilterGetChildPinCountfunctionreturns the number of pins of a given type that are currently instantiated on a given filter.
old-location: stream\ksfiltergetchildpincount.htm
tech.root: stream
ms.assetid: 29e78bc3-0dc2-4e76-b683-c1e9a2d454d4
ms.date: 04/23/2018
keywords: ["KsFilterGetChildPinCount function"]
ms.keywords: KsFilterGetChildPinCount, KsFilterGetChildPinCount function [Streaming Media Devices], avfunc_cddbf6bc-da19-47a6-96d5-0d4151e70ff8.xml, ks/KsFilterGetChildPinCount, stream.ksfiltergetchildpincount
f1_keywords:
 - "ks/KsFilterGetChildPinCount"
 - "KsFilterGetChildPinCount"
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
- KsFilterGetChildPinCount
targetos: Windows
req.typenames: 
---

# KsFilterGetChildPinCount function


## -description


The<b> KsFilterGetChildPinCount</b><b></b>function<b></b>returns the number of pins of a given type that are currently instantiated on a given filter.


## -parameters




### -param Filter [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter">KSFILTER</a> structure for which to find the number of instantiated pins of type <i>PinID</i>.


### -param PinId [in]

The pin type for which to find the number of instantiated pins. <i>PinID</i> is an index into the array of pin descriptors for the filter to which the pin belongs.


## -returns



<b>KsFilterGetChildPinCount</b> returns the number of pins of type <i>PinID</i> that are currently instantiated on <i>Filter</i>. If no such pins exist or if <i>PinID</i> is out of range, zero is returned.




## -remarks



The count returned by this call is guaranteed to be correct only if the function is called while the filter control mutex is held. The count remains correct after the call as long as this mutex continues to be held. As soon as the mutex is released, other pins can be added or removed, thereby altering the actual pin count.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/mutexes-in-avstream">Mutexes in AVStream</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter">KSFILTER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_kspin">KSPIN</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksfiltergetfirstchildpin">KsFilterGetFirstChildPin</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kspingetnextsiblingpin">KsPinGetNextSiblingPin</a>
 

 


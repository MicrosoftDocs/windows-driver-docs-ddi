---
UID: NF:ks.KsPinDataIntersection
title: KsPinDataIntersection function (ks.h)
description: The KsPinDataIntersection function handles the KSPROPERTY_PIN_DATAINTERSECTION property through a callback function and performs much of the initial validation of the parameters that are passed.
old-location: stream\kspindataintersection.htm
tech.root: stream
ms.assetid: e4bf090d-35ec-42fd-8b6e-ce51734adba5
ms.date: 04/23/2018
keywords: ["KsPinDataIntersection function"]
ms.keywords: KsPinDataIntersection, KsPinDataIntersection function [Streaming Media Devices], ks/KsPinDataIntersection, ksfunc_33b743b3-4045-49cb-a5d4-f6aede715223.xml, stream.kspindataintersection
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
 - KsPinDataIntersection
 - ks/KsPinDataIntersection
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsPinDataIntersection
---

# KsPinDataIntersection function


## -description

The <b>KsPinDataIntersection</b> function handles the <a href="/windows-hardware/drivers/stream/ksproperty-pin-dataintersection">KSPROPERTY_PIN_DATAINTERSECTION</a> property through a callback function and performs much of the initial validation of the parameters that are passed. <b>KsPinDataIntersection</b> calls the minidriver-defined <a href="/windows-hardware/drivers/ddi/ks/nc-ks-pfnksintersecthandler">KStrIntersectHandler</a> callback function with each potential data range after matching it to the list of data ranges assigned to that pin factory.

## -parameters

### -param Irp 

[in]
Specifies the IRP that describes the property request.

### -param Pin 

[in]
Specifies the specific property that is being queried.

### -param Data 

[out, optional]
Specifies the pin property-specific data.

### -param DescriptorsCount 

[in]
Specifies the number of descriptor structures.

### -param Descriptor 

[in]
Specifies the pointer to the list of pin information structures.

### -param IntersectHandler 

[in]
Specifies the minidriver-defined <a href="/windows-hardware/drivers/ddi/ks/nc-ks-pfnksintersecthandler">KStrIntersectHandler</a> callback function to compare a data range.

## -returns

The <b>KsPinDataIntersection</b> function returns STATUS_SUCCESS if a matching range is found, STATUS_NO_MATCH if no matching range was found, or an error specific to the property being handled. The minidriver-defined <i><u>KStrIntersectHandler</u></i> intersection handler provided to <b>KsPinDataIntersection</b> is called with each data range supplied by the caller until either a match is found or an error occurs.

Note that the minidriver-defined <a href="/windows-hardware/drivers/ddi/ks/nc-ks-pfnksintersecthandler">KStrIntersectHandler</a> callback function has its own set of return values.

## -remarks

A match can occur under three conditions: if the major format of the range passed is a wildcard or matches a pin factory range, if the subformat is a wildcard or matches, and if the specifier is a wildcard or matches. Since the data range size may be variable, it is not validated beyond checking that it is at least the size of a <a href="/previous-versions/ff561658(v=vs.85)">KSDATARANGE</a> structure.

## -see-also

<a href="/previous-versions/ff561658(v=vs.85)">KSDATARANGE</a>



<a href="/windows-hardware/drivers/ddi/ks/nc-ks-pfnksintersecthandler">KStrIntersectHandler</a>
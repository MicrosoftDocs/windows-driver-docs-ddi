---
UID: NS:ks.__unnamed_struct_22
title: KSP_TIMEFORMAT (ks.h)
description: The KSP_TIMEFORMAT structure corresponds to KSPROPERTY_MEDIASEEKING_CONVERTTIMEFORMAT.
old-location: stream\ksp_timeformat.htm
tech.root: stream
ms.assetid: 18ce5fc5-927c-4261-8966-bb12849b95c9
ms.date: 04/23/2018
ms.keywords: "*PKSP_TIMEFORMAT, KSP_TIMEFORMAT, KSP_TIMEFORMAT structure [Streaming Media Devices], PKSP_TIMEFORMAT, PKSP_TIMEFORMAT structure pointer [Streaming Media Devices], ks-struct_086a975b-f249-44e9-b1fa-4a945509722e.xml, ks/KSP_TIMEFORMAT, ks/PKSP_TIMEFORMAT, stream.ksp_timeformat"
f1_keywords:
 - "ks/KSP_TIMEFORMAT"
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ks.h
api_name:
- KSP_TIMEFORMAT
product:
- Windows
targetos: Windows
req.typenames: KSP_TIMEFORMAT, *PKSP_TIMEFORMAT
---

# KSP_TIMEFORMAT structure


## -description


The KSP_TIMEFORMAT structure corresponds to <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-mediaseeking-converttimeformat">KSPROPERTY_MEDIASEEKING_CONVERTTIMEFORMAT</a>.


## -struct-fields




### -field Property

Specifies a <a href="https://docs.microsoft.com/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a> structure.


### -field SourceFormat

Pointer to a GUID that specifies the format to convert. If <b>NULL</b>, the current format is used.


### -field TargetFormat

Pointer to a GUID that specifies the target format. If <b>NULL</b>, the current format is used.


### -field Time

Specifies the time value to convert.


## -remarks



The fields of the structure correspond one to one with DirectShow's IMediaSeeking::ConvertTimeFormat.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-mediaseeking-converttimeformat">KSPROPERTY_MEDIASEEKING_CONVERTTIMEFORMAT</a>
 

 


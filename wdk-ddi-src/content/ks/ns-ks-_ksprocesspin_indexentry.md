---
UID: NS:ks._KSPROCESSPIN_INDEXENTRY
title: _KSPROCESSPIN_INDEXENTRY (ks.h)
description: The KSPROCESSPIN_INDEXENTRY structure is used in Filter-Centric Processing to bring together all of the input and output pins in one context.
old-location: stream\ksprocesspin_indexentry.htm
tech.root: stream
ms.assetid: 8fa26442-66a3-4eeb-89d4-21418d60a1af
ms.date: 04/23/2018
ms.keywords: "*PKSPROCESSPIN_INDEXENTRY, KSPROCESSPIN_INDEXENTRY, KSPROCESSPIN_INDEXENTRY structure [Streaming Media Devices], PKSPROCESSPIN_INDEXENTRY, PKSPROCESSPIN_INDEXENTRY structure pointer [Streaming Media Devices], _KSPROCESSPIN_INDEXENTRY, avstruct_c32acda3-bab1-4077-a834-4b44a92524db.xml, ks/KSPROCESSPIN_INDEXENTRY, ks/PKSPROCESSPIN_INDEXENTRY, stream.ksprocesspin_indexentry"
ms.topic: struct
f1_keywords:
 - "ks/KSPROCESSPIN_INDEXENTRY"
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and in Microsoft DirectX 8.0 and later versions.
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
- KSPROCESSPIN_INDEXENTRY
product:
- Windows
targetos: Windows
req.typenames: KSPROCESSPIN_INDEXENTRY, *PKSPROCESSPIN_INDEXENTRY
---

# _KSPROCESSPIN_INDEXENTRY structure


## -description


The KSPROCESSPIN_INDEXENTRY structure is used in <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/filter-centric-processing">Filter-Centric Processing</a> to bring together all of the input and output pins in one context.


## -struct-fields




### -field Pins

A pointer to an array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_ksprocesspin">KSPROCESSPIN</a> structures. The array contains a listing of the instances of the given pin.


### -field Count

This member specifies the number of process pins in <i>Pins</i> that are currently instantiated.


## -remarks



This pointer table is indexed in order of the pins described in the pin descriptor table for the corresponding filter. The first pin described in the descriptor table has the first entry in the index table passed to the processing dispatch. See the processing dispatch in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_kspin_dispatch">KSPIN_DISPATCH</a>.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/filter-centric-processing">Filter-Centric Processing</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_ksprocesspin">KSPROCESSPIN</a>
 

 


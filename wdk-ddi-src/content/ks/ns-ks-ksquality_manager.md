---
UID: NS:ks.__unnamed_struct_54
title: KSQUALITY_MANAGER (ks.h)
description: The KSQUALITY_MANAGER structure is used with the KSPROPERTY_STREAM_QUALITY property and contains the handle of the quality manager sink and a context to pass in the quality complaints.
old-location: stream\ksquality_manager.htm
tech.root: stream
ms.assetid: 33e66fa0-53d6-400a-a03b-6d7b3fd01ace
ms.date: 04/23/2018
ms.keywords: "*PKSQUALITY_MANAGER, KSQUALITY_MANAGER, KSQUALITY_MANAGER structure [Streaming Media Devices], PKSQUALITY_MANAGER, PKSQUALITY_MANAGER structure pointer [Streaming Media Devices], ks-struct_97f36a6a-6d00-4cec-b13d-8f039b54c5a8.xml, ks/KSQUALITY_MANAGER, ks/PKSQUALITY_MANAGER, stream.ksquality_manager"
f1_keywords:
 - "ks/KSQUALITY_MANAGER"
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
- KSQUALITY_MANAGER
product:
- Windows
targetos: Windows
req.typenames: KSQUALITY_MANAGER, *PKSQUALITY_MANAGER
---

# KSQUALITY_MANAGER structure


## -description


The KSQUALITY_MANAGER structure is used with the <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-stream-quality">KSPROPERTY_STREAM_QUALITY</a> property and contains the handle of the quality manager sink and a context to pass in the quality complaints.


## -struct-fields




### -field QualityManager

Specifies a handle to the quality manager sink receiving the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksquality">KSQUALITY</a> complaint structures.


### -field Context

Specifies the context parameter to use when reporting quality problems. The context is used by the quality manager to distinguish between various clients that can send complaints to the same file object.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-stream-quality">KSPROPERTY_STREAM_QUALITY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksquality">KSQUALITY</a>
 

 


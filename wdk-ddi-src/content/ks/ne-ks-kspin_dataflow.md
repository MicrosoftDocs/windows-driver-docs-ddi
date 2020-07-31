---
UID: NE:ks.__unnamed_enum_12
title: KSPIN_DATAFLOW (ks.h)
description: An instance of the KSPIN_DATAFLOW enumeration is returned by KSPROPERTY_PIN_DATAFLOW.
old-location: stream\kspin_dataflow.htm
tech.root: stream
ms.assetid: feab830d-8079-4051-8974-52905f845765
ms.date: 04/23/2018
keywords: ["KSPIN_DATAFLOW enumeration"]
ms.keywords: "*PKSPIN_DATAFLOW, KSPIN_DATAFLOW, KSPIN_DATAFLOW enumeration [Streaming Media Devices], KSPIN_DATAFLOW_IN, KSPIN_DATAFLOW_OUT, PKSPIN_DATAFLOW, PKSPIN_DATAFLOW enumeration pointer [Streaming Media Devices], ks-struct_2161b89b-ba7c-440a-9006-c3445b392b89.xml, ks/KSPIN_DATAFLOW, ks/KSPIN_DATAFLOW_IN, ks/KSPIN_DATAFLOW_OUT, ks/PKSPIN_DATAFLOW, stream.kspin_dataflow"
f1_keywords:
 - "ks/KSPIN_DATAFLOW"
 - "KSPIN_DATAFLOW"
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
- KSPIN_DATAFLOW
targetos: Windows
req.typenames: KSPIN_DATAFLOW, *PKSPIN_DATAFLOW
---

# KSPIN_DATAFLOW enumeration


## -description


An instance of the KSPIN_DATAFLOW enumeration is returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-pin-dataflow">KSPROPERTY_PIN_DATAFLOW</a>.


## -enum-fields




### -field KSPIN_DATAFLOW_IN

Indicates that the pin factory instantiates data sink pins. Such pins can only be connected to data source pins. 


### -field KSPIN_DATAFLOW_OUT

Indicates that the pin factory instantiates data source pins. Such pins can only be connected to data sink pins.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_stream_information">HW_STREAM_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_kspin">KSPIN</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-kspin_descriptor">KSPIN_DESCRIPTOR</a>
 

 


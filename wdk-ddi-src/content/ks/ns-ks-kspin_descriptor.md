---
UID: NS:ks.__unnamed_struct_35
title: KSPIN_DESCRIPTOR (ks.h)
description: The KSPIN_DESCRIPTOR structure describes the basic KSPROPSETID_Pin properties of a pin type.
old-location: stream\kspin_descriptor.htm
tech.root: stream
ms.assetid: 0e7fccd1-1ced-41e7-8e75-8f4fa496ea06
ms.date: 04/23/2018
ms.keywords: "*PKSPIN_DESCRIPTOR, KSPIN_DESCRIPTOR, KSPIN_DESCRIPTOR structure [Streaming Media Devices], PKSPIN_DESCRIPTOR, PKSPIN_DESCRIPTOR structure pointer [Streaming Media Devices], ks-struct_adeadb36-6cf2-4c36-a1b4-a7852e98303f.xml, ks/KSPIN_DESCRIPTOR, ks/PKSPIN_DESCRIPTOR, stream.kspin_descriptor"
ms.topic: struct
f1_keywords:
 - "ks/KSPIN_DESCRIPTOR"
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
- KSPIN_DESCRIPTOR
product:
- Windows
targetos: Windows
req.typenames: KSPIN_DESCRIPTOR, *PKSPIN_DESCRIPTOR
---

# KSPIN_DESCRIPTOR structure


## -description


The KSPIN_DESCRIPTOR structure describes the basic <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/kspropsetid-pin">KSPROPSETID_Pin</a> properties of a pin type.


## -struct-fields




### -field InterfacesCount

Specifies the size of the array pointed to by <b>Interfaces</b>.


### -field Interfaces

An array of <a href="https://docs.microsoft.com/previous-versions/ff563537(v=vs.85)">KSPIN_INTERFACE</a> structures specifying the interfaces supported by this pin type.


### -field MediumsCount

Specifies the number of elements in the array pointed to by <b>Mediums</b>.


### -field Mediums

An array of <a href="https://docs.microsoft.com/previous-versions/ff563538(v=vs.85)">KSPIN_MEDIUM</a> structures specifying the mediums supported by this pin type.


### -field DataRangesCount

Specifies the size of the array pointed to by <b>DataRanges</b>.


### -field DataRanges

An array of <a href="https://docs.microsoft.com/previous-versions/ff561658(v=vs.85)">KSDATARANGE</a> structures specifying the data ranges supported by this pin type.


### -field DataFlow

Specifies either <b>KSPIN_DATAFLOW_IN</b> or KSPIN_DATAFLOW_OUT. See <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-pin-dataflow">KSPROPERTY_PIN_DATAFLOW</a>.


### -field Communication

Specifies KSPIN_COMMUNICATION_NONE, KSPIN_COMMUNICATION_SINK, KSPIN_COMMUNICATION_SOURCE, KSPIN_COMMUNICATION_BOTH or KSPIN_COMMUNICATION_BRIDGE. See <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-pin-communication">KSPROPERTY_PIN_COMMUNICATION</a> for the meaning of each value.


### -field Category

Specifies a pointer to a KS pin category GUID. The KS pin category GUID identifies the general category of functionality that the pin provides. Examples of KS pin category GUIDs are KSNODETYPE_SPEAKER, KSNODETYPE_HEADPHONES, and KSNODETYPE_MICROPHONE, which are all defined in <i>Ksmedia.h</i>. Also see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/pin-category-property">Pin Category Property</a>.


### -field Name

Specifies the GUID of the localized Unicode string name for the pin type, stored in the Registry.


### -field Reserved

Not used.  A member of an unnamed union used to force proper alignment on the unnamed structure.


### -field ConstrainedDataRangesCount

Specifies the number of entries in the array pointed to by <b>ConstrainedDataRanges</b>.


### -field ConstrainedDataRanges

Points to an array of <a href="https://docs.microsoft.com/previous-versions/ff561658(v=vs.85)">KSDATARANGE</a> structures. Indicates the set of data ranges the pin type currently supports, based on the driver's internal state.


## -remarks



Drivers typically define one KSPIN_DESCRIPTOR structure for each pin type they support.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/ff561658(v=vs.85)">KSDATARANGE</a>



<a href="https://docs.microsoft.com/previous-versions/ff563538(v=vs.85)">KSPIN_MEDIUM</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-pin-communication">KSPROPERTY_PIN_COMMUNICATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-pin-dataflow">KSPROPERTY_PIN_DATAFLOW</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/kspropsetid-pin">KSPROPSETID_Pin</a>
 

 


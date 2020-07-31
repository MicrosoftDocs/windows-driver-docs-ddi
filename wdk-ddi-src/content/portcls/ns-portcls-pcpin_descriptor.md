---
UID: NS:portcls.__unnamed_struct_4
title: PCPIN_DESCRIPTOR (portcls.h)
description: The PCPIN_DESCRIPTOR structure describes a pin factory.
old-location: audio\pcpin_descriptor.htm
tech.root: audio
ms.assetid: 1eeee706-b7f4-4b4d-93c8-969eac7c56d9
ms.date: 05/08/2018
keywords: ["PCPIN_DESCRIPTOR structure"]
ms.keywords: "*PPCPIN_DESCRIPTOR, PCPIN_DESCRIPTOR, PCPIN_DESCRIPTOR structure [Audio Devices], PPCPIN_DESCRIPTOR, PPCPIN_DESCRIPTOR structure pointer [Audio Devices], audio.pcpin_descriptor, audpc-struct_475141ba-bf2e-4425-92ac-02649248e19f.xml, portcls/PCPIN_DESCRIPTOR, portcls/PPCPIN_DESCRIPTOR"
f1_keywords:
 - "portcls/PCPIN_DESCRIPTOR"
 - "PCPIN_DESCRIPTOR"
req.header: portcls.h
req.include-header: Portcls.h
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
- portcls.h
api_name:
- PCPIN_DESCRIPTOR
targetos: Windows
req.typenames: PCPIN_DESCRIPTOR, *PPCPIN_DESCRIPTOR
---

# PCPIN_DESCRIPTOR structure


## -description


The <b>PCPIN_DESCRIPTOR</b> structure describes a pin factory.


## -struct-fields




### -field MaxGlobalInstanceCount

Specifies the global maximum number of times that this pin type can be instantiated. The global maximum counts the number of pin instances that the adapter driver can support across all instances of the filter. The count can be set to zero to indicate that the pin cannot be instantiated. A value of ULONG(-1) indicates the pin can be instantiated any number of times. Any other value indicates a specific number of times that the pin can be instantiated.


### -field MaxFilterInstanceCount

Specifies the maximum number times that the pin can be instantiated on a single instance of the filter. The count can be set to zero to indicate that the pin cannot be instantiated. A value of ULONG(-1) indicates the pin can be instantiated any number of times. Any other value indicates a specific number of times that the pin can be instantiated.


### -field MinFilterInstanceCount

Specifies the minimum number of times that the pin needs to be instantiated on an instance of the filter. This member is a definite lower bound on the number of instances of a pin that must exist in order for a filter to be able to function.


### -field AutomationTable

Pointer to the automation table. This member is a pointer to a structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/ns-portcls-pcautomation_table">PCAUTOMATION_TABLE</a>. The pointer can be <b>NULL</b> to indicate that no automation is supported. The automation table specifies the handlers for the properties and events belonging to the pin instance.


### -field KsPinDescriptor

Describes the pin factory. This member is a structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-kspin_descriptor">KSPIN_DESCRIPTOR</a>. A pin factory can have zero interfaces and zero mediums. The list of interfaces is ignored in all cases. The standard-medium list will default to a list containing only device I/O (KSMEDIUM_STANDARD_DEVIO).


## -remarks



This structure is used to describe each of the pin factories that a miniport driver implements. The driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/ns-portcls-pcfilter_descriptor">PCFILTER_DESCRIPTOR</a> structure contains a pointer to an array of <b>PCPIN_DESCRIPTOR</b> structures. The number of elements in the array is equal to the number of pin factories in the filter.

The <b>MaxGlobalInstanceCount</b>, <b>MaxFilterInstanceCount</b>, and <b>MinFilterInstanceCount</b> members are maximum and minimum counts that describe the pin's resource restrictions and functional requirements. An autoinitialized <b>PCPIN_DESCRIPTOR</b> array can present only a static estimate of the available pin resources. The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-ipincount-pincount">IPinCount::PinCount</a> method provides a means for the driver to revise its list of available pin resources dynamically as pins are allocated and freed.

The <b>MaxGlobalInstanceCount</b> value is similar in meaning to:

<ul>
<li>
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-ipincount-pincount">PinCount</a> method's <i>GlobalPossible</i> call parameter.

</li>
<li>
The <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-pin-globalcinstances">KSPROPERTY_PIN_GLOBALCINSTANCES</a> property value (the KSPIN_CINSTANCES structure's <b>PossibleCount</b> member).

</li>
</ul>
The <b>MaxFilterInstanceCount</b> value is similar in meaning to:

<ul>
<li>
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-ipincount-pincount">PinCount</a> method's <i>FilterPossible</i> call parameter.

</li>
<li>
The <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-pin-cinstances">KSPROPERTY_PIN_CINSTANCES</a> property value (the KSPIN_CINSTANCES structure's <b>PossibleCount</b> member).

</li>
</ul>
The <b>MinFilterInstanceCount</b> value is similar in meaning to:

<ul>
<li>
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-ipincount-pincount">PinCount</a> method's <i>FilterNecessary</i> call parameter.

</li>
<li>
The <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-pin-necessaryinstances">KSPROPERTY_PIN_NECESSARYINSTANCES</a> property value.

</li>
</ul>
When describing a bridge pin (see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/audio-filter-graphs">Audio Filter Graphs</a>), set <b>MaxGlobalInstanceCount</b>, <b>MaxFilterInstanceCount</b>, and <b>MinFilterInstanceCount</b> to zero, and set <b>AutomationTable</b> to <b>NULL</b>.

For a simple code example that shows how the <b>PCPIN_DESCRIPTOR</b> structure is used, see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/exposing-filter-topology">Exposing Filter Topology</a>.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/pin-factories">Pin Factories</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-ipincount-pincount">IPinCount::PinCount</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-kspin_descriptor">KSPIN_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-pin-cinstances">KSPROPERTY_PIN_CINSTANCES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-pin-globalcinstances">KSPROPERTY_PIN_GLOBALCINSTANCES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-pin-necessaryinstances">KSPROPERTY_PIN_NECESSARYINSTANCES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/ns-portcls-pcautomation_table">PCAUTOMATION_TABLE</a>
 

 


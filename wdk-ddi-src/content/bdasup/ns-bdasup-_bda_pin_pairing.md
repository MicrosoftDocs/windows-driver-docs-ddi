---
UID: NS:bdasup._BDA_PIN_PAIRING
title: _BDA_PIN_PAIRING (bdasup.h)
description: The BDA_PIN_PAIRING structure describes the topology between a pair of input and output pins.
old-location: stream\bda_pin_pairing.htm
tech.root: stream
ms.assetid: 0d05455d-32ea-4f88-8752-7f5fe40b8b29
ms.date: 04/23/2018
ms.keywords: "*PBDA_PIN_PAIRING, BDA_PIN_PAIRING, BDA_PIN_PAIRING structure [Streaming Media Devices], PBDA_PIN_PAIRING, PBDA_PIN_PAIRING structure pointer [Streaming Media Devices], _BDA_PIN_PAIRING, bdaref_b007d58d-86c0-4653-867a-78ef5be2f260.xml, bdasup/BDA_PIN_PAIRING, bdasup/PBDA_PIN_PAIRING, stream.bda_pin_pairing"
ms.topic: struct
req.header: bdasup.h
req.include-header: Bdasup.h
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	bdasup.h
api_name:
-	BDA_PIN_PAIRING
product:
- Windows
targetos: Windows
req.typenames: BDA_PIN_PAIRING, *PBDA_PIN_PAIRING
---

# _BDA_PIN_PAIRING structure


## -description


The BDA_PIN_PAIRING structure describes the topology between a pair of input and output pins. 


## -struct-fields




### -field ulInputPin

Index of the element in the zero-based array of pin types (KSPIN_DESCRIPTOR_EX array) that indicates the input pin of the pair. 


### -field ulOutputPin

Index of the element in the zero-based array of pin types (KSPIN_DESCRIPTOR_EX array) that indicates the output pin of the pair.


### -field ulcMaxInputsPerOutput

Maximum number of input pins per output pin. The network provider creates duplicates of nodes that are controlled by the input pin depending on the value specified in <b>ulcMaxInputsPerOutput</b>.


### -field ulcMinInputsPerOutput

Minimum number of input pins per output pin. The network provider creates duplicates of nodes that are controlled by the input pin depending on the value specified in <b>ulcMinInputsPerOutput</b>.


### -field ulcMaxOutputsPerInput

Maximum number of output pins per input pin. The network provider creates duplicates of nodes that are controlled by the output pin depending on the value specified in <b>ulcMaxOutputsPerInput</b>.


### -field ulcMinOutputsPerInput

Minimum number of output pins per input pin. The network provider creates duplicates of nodes that are controlled by the output pin depending on the value specified in <b>ulcMinOutputsPerInput</b>.


### -field ulcTopologyJoints

Number of joints in the <b>pTopologyJoints</b> array.


### -field pTopologyJoints

Array of joint values. The value given to a joint corresponds to the index of an element in a array of template connections (KSTOPOLOGY_CONNECTION or BDA_TEMPLATE_CONNECTION array). A topology joint marks the point in the template topology where control of nodes switches from the input pin to the output pin. Those nodes that occur upstream of the topology joint are controlled through the input pin. Those nodes that occur downstream of the topology joint are controlled through the output pin.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556523">BDA_FILTER_TEMPLATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556558">BDA_TEMPLATE_CONNECTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563534">KSPIN_DESCRIPTOR_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567148">KSTOPOLOGY_CONNECTION</a>
 

 


---
UID: NS:bdasup._BDA_PIN_PAIRING
title: "_BDA_PIN_PAIRING"
author: windows-driver-content
description: The BDA_PIN_PAIRING structure describes the topology between a pair of input and output pins.
old-location: stream\bda_pin_pairing.htm
old-project: stream
ms.assetid: 0d05455d-32ea-4f88-8752-7f5fe40b8b29
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.bda_pin_pairing, bdasup/PBDA_PIN_PAIRING, PBDA_PIN_PAIRING structure pointer [Streaming Media Devices], BDA_PIN_PAIRING, BDA_PIN_PAIRING structure [Streaming Media Devices], bdasup/BDA_PIN_PAIRING, _BDA_PIN_PAIRING, PBDA_PIN_PAIRING, *PBDA_PIN_PAIRING, bdaref_b007d58d-86c0-4653-867a-78ef5be2f260.xml
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	bdasup.h
apiname:
-	BDA_PIN_PAIRING
product: Windows
targetos: Windows
req.typenames: BDA_PIN_PAIRING, *PBDA_PIN_PAIRING
---

# _BDA_PIN_PAIRING structure


## -description


The BDA_PIN_PAIRING structure describes the topology between a pair of input and output pins. 


## -syntax


````
typedef struct _BDA_PIN_PAIRING {
  ULONG       ulInputPin;
  ULONG       ulOutputPin;
  ULONG       ulcMaxInputsPerOutput;
  ULONG       ulcMinInputsPerOutput;
  ULONG       ulcMaxOutputsPerInput;
  ULONG       ulcMinOutputsPerInput;
  ULONG       ulcTopologyJoints;
  const ULONG *pTopologyJoints;
} BDA_PIN_PAIRING, *PBDA_PIN_PAIRING;
````


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

<a href="..\ks\ns-ks-_kspin_descriptor_ex.md">KSPIN_DESCRIPTOR_EX</a>

<a href="..\ks\ns-ks-kstopology_connection.md">KSTOPOLOGY_CONNECTION</a>

<a href="..\bdasup\ns-bdasup-_bda_filter_template.md">BDA_FILTER_TEMPLATE</a>

<a href="..\bdatypes\ns-bdatypes-_bda_template_connection.md">BDA_TEMPLATE_CONNECTION</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20BDA_PIN_PAIRING structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


---
UID: NS:bdamedia._KSP_BDA_NODE_PIN
title: "_KSP_BDA_NODE_PIN"
author: windows-driver-content
description: The KSP_BDA_NODE_PIN structure describes a property request to retrieve the controlling pin for a node.
old-location: stream\ksp_bda_node_pin.htm
old-project: stream
ms.assetid: 684a0b26-0e25-44fb-bca9-c86ac029b3b8
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSP_BDA_NODE_PIN, KSP_BDA_NODE_PIN, KSP_BDA_NODE_PIN structure [Streaming Media Devices], PKSP_BDA_NODE_PIN, PKSP_BDA_NODE_PIN structure pointer [Streaming Media Devices], _KSP_BDA_NODE_PIN, bdamedia/KSP_BDA_NODE_PIN, bdamedia/PKSP_BDA_NODE_PIN, bdaref_5e3a84db-906c-4d12-863d-9a77b2f7d78c.xml, stream.ksp_bda_node_pin"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bdamedia.h
req.include-header: Bdamedia.h
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
-	bdamedia.h
api_name:
-	KSP_BDA_NODE_PIN
product: Windows
targetos: Windows
req.typenames: KSP_BDA_NODE_PIN, *PKSP_BDA_NODE_PIN
---

# _KSP_BDA_NODE_PIN structure


## -description


The KSP_BDA_NODE_PIN structure describes a property request to retrieve the controlling pin for a node. 


## -syntax


````
typedef struct _KSP_BDA_NODE_PIN {
  KSPROPERTY Property;
  ULONG      ulNodeType;
  ULONG      ulInputPinId;
  ULONG      ulOutputPinId;
} KSP_BDA_NODE_PIN, *PKSP_BDA_NODE_PIN;
````


## -struct-fields




### -field Property

KSPROPERTY structure that describes the property and request type of the property request.


### -field ulNodeType

Index of the element in the zero-based array of internal node types (KSNODE_DESCRIPTOR array) that specifies the node type for which to retrieve the controlling pin. 


### -field ulInputPinId

Identifier of an input pin of the filter.


### -field ulOutputPinId

Identifier of an output pin of the filter.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566561">KSPROPSETID_BdaTopology</a>



<a href="..\bdasup\nf-bdasup-bdapropertygetcontrollingpinid.md">BdaPropertyGetControllingPinId</a>



<a href="..\ks\ns-ks-_ksnode_descriptor.md">KSNODE_DESCRIPTOR</a>



 

 


